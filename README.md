# Secret-Harbor
Heroku app using [Tesseract OCR](https://code.google.com/p/tesseract-ocr/) written in Python and based on the [Flask web microframework](http://flask.pocoo.org/). Only English and Finnish language are supported.

## Configuration
As can be seen in the file `.buildpacks`, in addition to the default [heroku-python-tesseract](https://github.com/heroku/heroku-python-tesseract), this app also requires the custom [heroku-buildpack-tesseract](https://github.com/matteotiziano/heroku-buildpack-tesseract).  

Before deploying the app, you should add a configuration variable to allow for multiple buildpacks as   
```
heroku config:set
BUILDPACK_URL=https://github.com/ddollar/heroku-buildpack-multi
```

or (equivalently) change the default buildpack as   
```
heroku buildpacks:set https://github.com/ddollar/heroku-buildpack-multi
```

## How to use
Let us assume you have deployed this app in Heroku and you called it `your-heroku-app`.

The app provides a test client `https://your-heroku-app.herokuapp.com/test` and a REST method `https://your-heroku-app.herokuapp.com/process`: the client provides the input file (image or PDF), whereas the REST method returns a JSON object containing the OCR of the input.

This app is available at https://secret-harbor.herokuapp.com/test.

## Licence
MIT Licence. Copyright (c) 2015 Matteo Maggioni
