This project hosts the [Joseki.jl](https://github.com/amellnik/Joseki.jl)
example app on Heroku using a [julia buildpack](https://github.com/Optomatica/heroku-buildpack-julia).


Steps:
```
git clone https://github.com/amellnik/Joseki.jl.git
cd Joseki.jl/examples/heroku-buildpack-example
HEROKU_APP_NAME=my-app-name
heroku create $HEROKU_APP_NAME --buildpack https://github.com/Optomatica/heroku-buildpack-julia.git
git push heroku master
heroku open -a $HEROKU_APP_NAME
heroku logs -tail -a $HEROKU_APP_NAME
```

Additional command line tests
```
curl $HEROKU_APP_NAME.herokuapp.com
curl -X GET $HEROKU_APP_NAME'.herokuapp.com/pow?x=3&y=4'
curl -X POST $HEROKU_APP_NAME'.herokuapp.com/bin' -H "Content-Type: application/json" --data '{"n":5,"k":2}'
```
