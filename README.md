# Deploy Deep learning models as a REST API

This repository helps in deploying deep learning based models in the production.

## Getting started

Install Tensorflow, Keras, Flask and Pillow.

```sh
$ pip install flask requests pillow
```

## Starting the Keras server

The Flask + Keras server can be started by running:

```sh
$ python mainapp.py 
Using TensorFlow backend.
 * Loading Keras model and Flask starting server...please wait until server has fully started
...
 * Running on http://127.0.0.1:5000
```

You can now access the REST API via `http://127.0.0.1:5000`.

## Submitting requests to the Keras server

Requests can be submitted via cURL or web browser. 

1. Using Curl

```sh
$ curl -X POST -F image=@dog.jpg 'http://localhost:5000/predict'
{
  "predictions": [
    {
      "label": "beagle", 
      "probability": 0.9901360869407654
    }, 
    {
      "label": "Walker_hound", 
      "probability": 0.002396771451458335
    }, 
    {
      "label": "pot", 
      "probability": 0.0013951235450804234
    }, 
    {
      "label": "Brittany_spaniel", 
      "probability": 0.001283277408219874
    }, 
    {
      "label": "bluetick", 
      "probability": 0.0010894243605434895
    }
  ], 
  "success": true
}
```

2. Web browser:

```sh
Upload image and get the results in json format in the browser. 

```

### References
```sh
Flask hosting options
1. [http://flask.pocoo.org/docs/1.0/deploying/](http://flask.pocoo.org/docs/1.0/deploying/)

Guide to setup Nginx and uWGSI
2. [https://hackernoon.com/a-guide-to-scaling-machine-learning-models-in-production-aa8831163846](https://hackernoon.com/a-guide-to-scaling-machine-learning-models-in-production-aa8831163846)

Deploy Your First Deep Learning Model On Kubernetes With Python, Keras, Flask, and Docker
3. [https://medium.com/analytics-vidhya/deploy-your-first-deep-learning-model-on-kubernetes-with-python-keras-flask-and-docker-575dc07d9e76](https://medium.com/analytics-vidhya/deploy-your-first-deep-learning-model-on-kubernetes-with-python-keras-flask-and-docker-575dc07d9e76)

Convert laptop/Desktop to host
4. [https://blog.mindorks.com/how-to-convert-your-laptop-desktop-into-a-server-and-host-internet-accessible-website-on-it-part-2-cdb4b3633fa9](https://blog.mindorks.com/how-to-convert-your-laptop-desktop-into-a-server-and-host-internet-accessible-website-on-it-part-2-cdb4b3633fa9)

5. To deploy model on AWS just configure Nginx and uWGSI and open port from instance settings.

API Design Guide
6. [https://www.fullstackpython.com/api-creation.html, https://programminghistorian.org/en/lessons/creating-apis-with-python-and-flask](https://www.fullstackpython.com/api-creation.html, https://programminghistorian.org/en/lessons/creating-apis-with-python-and-flask)

Outh setup Guide
7. [https://github.com/miguelgrinberg/REST-auth](https://github.com/miguelgrinberg/REST-auth), [https://flask-httpauth.readthedocs.io/en/latest/](https://flask-httpauth.readthedocs.io/en/latest/),[https://realpython.com/token-based-authentication-with-flask/](https://realpython.com/token-based-authentication-with-flask/)

