# project4-Deploy-web-application-using-aws-serverless-architecture-
Deploy web application using serverless application

In this project we will use 5 AWS services to build end to end application. AWS Amplify, AWS Lambda, Amazon API Gateway, Amazon DynamoDB, AWS IAM.

![Web application using aws serverless architecture](https://github.com/user-attachments/assets/db2da0db-7929-466e-9d1e-1e94a9d56f63)



Steps to complete the project:

1. Away to create/host a webpage.

2. Away to invoke the math functionality.

3. Away to do the math

4. Store the result

5. Away to handle permissions


Step 1: Start with create/host the webpage by using AWS Amplify

First lets use a text editor to create a simple index-original.html page by using code given in the file. And send to compressed folder to zip the file.

![image](https://github.com/user-attachments/assets/6540ad36-4581-4f92-8a75-31e8b456a9a1)


Now go to AWS Console, Navigate to AWS Amplify. create a new app, here we will host the webapp. Give the app a name and env name as dev. Drag the zipfile. save and deploy.

![image](https://github.com/user-attachments/assets/2bfab63d-d3f2-494b-9c85-d0333619e89e)

After deploying, we will get the url. open the url with a new tab.

![image](https://github.com/user-attachments/assets/596c1113-a97a-4884-841c-2987c962d4cc)

Skip the step 2 and do the step 3 first

Step 3: Navigate to Lambda create a function to do math. We use Lambda to run the code serverlessly to some trigger. create function and run the sample code. save the code and deploy. Do the test by naming test event, give values for base and exponent.

![image](https://github.com/user-attachments/assets/50ea3aaa-1cf7-4730-b501-819018ba2493)


![image](https://github.com/user-attachments/assets/0d72c393-48fc-4c6f-8881-f23f5cb6bafe)

step 2: Invoke the math functionality by using API gateway. API gateway used to build http, rest and websocket api's. Create API by using rest api, give a name and create.
In the resources create method, kind of method is post integrate with lambda function, click save.

![image](https://github.com/user-attachments/assets/217fdbd3-3d28-4103-95e8-881eae8d0915)

Next click on stage, setup a new stage dev and deploy. copy the apigateway: url and save it in notepad.

![image](https://github.com/user-attachments/assets/1c58f3c6-2720-4d2e-8ad1-b8d23d793258)

do post method test to check whether the lambda is working or not.

![image](https://github.com/user-attachments/assets/8b2ddd74-6931-4b97-9b2d-c524d32f0bbe)

Step4 and step 5:  store the result in database. Here we use Dynamodb. It is a key value or no sql database. we have to permissions to lambda function to write to database.
Navigate to Dynamodb. Create table giving table name as powerofmathdb, partition key is Id. grab the arn from it and save it.

![image](https://github.com/user-attachments/assets/53c0b42a-cdc7-4af6-8812-057f3f65b27c)

Navigate to lambda, go to permissions and add role policy by creating jsonpolicy. Here we are giving permissions to lambda to allow dynamodb to write the database in its table. In the code, resource : copy dynamodb arn.

![image](https://github.com/user-attachments/assets/76047c7e-37ac-4d80-ae29-56fe8a7fd786)

Change the Lambda function code to final. 

![image](https://github.com/user-attachments/assets/bc183b48-f4d2-4c62-9972-26f2ea395eb7)


Save, Deploy and test.

![image](https://github.com/user-attachments/assets/322ef63e-b928-4790-a8f3-c02fb8465929)


Next check the dynamodb table item to see the database.

![image](https://github.com/user-attachments/assets/f83804bd-ce2b-4b95-ae1e-81ff875d4d23)


lets connect the amplify and api gateway. go to index.html, paste the final code. here update of css code, in body update the api gateway url. and save it and make it a zip file. Again redeploy in Amplify.

![image](https://github.com/user-attachments/assets/7c4be72f-f10d-4591-95e3-37cd6cf1dfcc)

![image](https://github.com/user-attachments/assets/a816d492-ce6a-46f0-ade6-e5a1795dab04)

Now use the url from Amplify and see the result.

![image](https://github.com/user-attachments/assets/963b0932-e309-40f8-99fe-2895d06b57c0)



















