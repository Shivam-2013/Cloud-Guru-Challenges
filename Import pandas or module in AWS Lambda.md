I have wasted a lot of time to check how we may import pandas or any other libraries in AWS lambda function. 
I hope readers issues/queries are resolved after reading this article.

AWS Lambda doesn't come with all the modules in python. Hence we need to include the those modules which we are using in our Lambda function. 
I have broken the implementation in steps.
      . 
In my case, I require Pandas, Numpy module to run my code. My lambda function is build on python 3.8 hence all the dependecies will be adjusted accordingly. Download the dependencies Pandas, Numpy. _For Pandas to run on Lambda, an additional support of Pytz library is also required._

**Version needs to download**
* https://pypi.org/project/numpy/#files
* https://pypi.org/project/pandas/#files
* https://pypi.org/project/pytz/#files

## STEP 1 - To get zip file with dependencies 

### Create an EC2 instance 
Launch a linux EC2 instance using free tier only. Now SSH to EC2 instance

### Download
sudo wget `http url to the version which is to be downloaded`

### Create a folder with the name python.
sudo mkdir `python`

### Unzip the downloaded module in new folder python
sudo unzip `<filename>` -d `<path to python folder>`

### Zip the python folder
sudo zip -r `python.zip` `python`

### Copy the zip folder to S3 bucket
aws s3 cp python.zip s3://bucketname
or download the zip folder and upload the file in S3

## STEP 2 - Create a layer in Lambda function
Create a layer based on the S3 bucket

## STEP 3 - Layer in lambda
Use the layer created in the lambda function to import the library
