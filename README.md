# Deploying Flask App into EKS(AW0)


This project is containerize and deploy a Flask API to a Kubernetes cluster using Docker, AWS EKS, CodePipeline, and CodeBuild.

The Flask app that will be used for this project consists of a simple API with three endpoints:

- `GET '/'`: This is a simple health check, which returns the response 'Healthy'. 
- `POST '/auth'`: This takes a email and password as json arguments and returns a JWT based on a custom secret.
- `GET '/contents'`: This requires a valid JWT, and returns the un-encrpyted contents of that token. 

The app relies on a secret set as the environment variable `JWT_SECRET` to produce a JWT. The built-in Flask server is adequate for local development, but not production, so you will be using the production-ready [Gunicorn](https://gunicorn.org/) server when deploying the app.

## Project processing
1.  Fork this project to your Github account.
2.  Locally clone your forked version to begin working on the project.
3.  Run the app locally with flask Server for development purpose.
4.  Install Docker and use the docker file provided and create a container.
5.  Create an AWS Account.
6.  install AWS CLI 
7.  install KubeCli
8.  set up the AWS profile
9.  Create the EKS cluster and nodes using the docker file
10. Use the cloud formation template
11. Update all the trust store to add the role for EKS
12. Add the trust.json
13. Add the environment variable and also in buildspec.yml
14. deploy and extract the endpoint. 


## CI/CD Pipline

The setup of the project specified in the cloud formation will make sure where ever there is commit in the github, Automated build is triggered 
     
## Testing the new AWS Endpoints

I have included postman collection(ApiTest-Docker.postman_collection) in the repo for all the 3 endpoints. Just imp it with post and you are ready to go


## Reference
https://www.cnblogs.com/Liu-Hui/p/13388194.html - To solve the time problem
used Jet brains Docker plugin on Pycharm (veryuseful)
https://docs.aws.amazon.com/cli/latest/reference/ssm/put-parameter.html

