<!-- This is a template you can use for quick progress days. It removes a lot of the steps we encourage you to share in the longer template 000-DAY-ARTICLE-LONG-TEMPLATE.MD-->

# Continuation of serverless journey - running lambda functions in a Docker image (Part 1)

## Introduction

I am doing this because I think it's pretty common to put lambda functions inside of a Docker image, like a Node image or Node-alpine image.

I am only filing a short report on this today because I'm doing something that does not have a project idea in the #100DaysOfCloud ideas part and I'm documenting what I'm doing in order to perhaps create an issue/PR for it. As such, I didn't finish and now am out of time for the day to work on this.
## Cloud Research

- So far I had to add some new permissions to my IAM user that I am using. These permissions allow my IAM user to get and update repos on ECR. They also allow my IAM user to manipulate images on ECR.
- I then created a local project that contains the adder function used in day 7. My version is a Node.js version.
- As a result of this, I had to create a new Dockerfile. I just used a template from the Amazon docs and added a port exposure to it.
- I built the image with Docker and ran it locally. I also tested it with a curl.
- Now I have to push it to ECR and do the rest of the set-up.

## Next Steps

- I will finish this project tomorrow.
- I will look at some more lambda-related projects or start on Kubernetes deployments in aws.
