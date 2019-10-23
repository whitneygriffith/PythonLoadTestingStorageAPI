# About 

This project uses [Locust](https://locust.io/), a modern open source load testing tool that simulates distinct users to swarm your system simultaneously. 

The test implemented is to upload an image to an endpoint, ideally Azure Blob Storage.

## Configuration

Update [tests.py](./tests.py):
1. Add your service authentication key information to the header of the request in the ```putImage(self)``` function in the ```UserBehavior``` class. 
2. Update your host url in the ```APILocust``` class. 


## Create Virtualenv for python packages 
```virtualenv venv```

```source venv/bin/activate```

```pip install -r requirements.txt```

## Run Locust/Tests 

```locust --locustfile tests.py```

The local server can be seen at [http://localhost:8090](http://localhost:8090) or [http://000.0.0.1:8089/](http://000.0.0.0:8089/)

You will then be ask:
1. Number of Users to simulate 
2. Hatch Rate (number of users to spawn per second)

## Configure Tests 


### Tests Results 

For an [APIM](https://docs.microsoft.com/en-us/azure/api-management/) endpoint that stores the image payload in [Azure Blob Storage](https://azure.microsoft.com/en-us/services/storage/blobs/). 

![Result](./images/1000users.png)
With **1000 users spawned**, with at most **92.7 Requests per second**, the minimum response time was **6.316 seconds** and the maximum response time was **40.996 seconds**


![Result](./images/49users.png)
With **49 users spawned**, with at most **6.2 Requests per second**, the minimum response time was **68.93 ms** and the maximum response time was **1983 ms**


