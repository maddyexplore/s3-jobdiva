# s3-jobdiva
Pulling Data in S3 to Jobdiva portal

## Push the Docker to ECR
* login 

`aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 152050937447.dkr.ecr.us-east-1.amazonaws.com`

* Build the Image

`docker build -t dataload .`

* Tag the Image

`docker tag dataload:latest 152050937447.dkr.ecr.us-east-1.amazonaws.com/dataload:latest`

* Push in ECR

`docker push 152050937447.dkr.ecr.us-east-1.amazonaws.com/dataload:latest`

## To change bucket Name
* Go into the instance (dataload1)
* Go to /home/ubuntu/dataload
* Change the bucket Name in Line# 37 in main.py
* Build the Docker Image
`sudo docker build .`

* To run and test
`sudo docker run .`

## To Trigger Ecs 
* Go to the lambda function (dataload_ecs_trigger)
* change the range (Prefix of S3 Files in dataload Folder)
* Click test 


