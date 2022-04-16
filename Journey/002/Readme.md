<!-- This template removes the micro tutorial for a quicker post and removes images for a full template check out the 000-DAY-ARTICLE-LONG-TEMPLATE.MD-->
# Not-so easy to upload Docker image to ECR

## Introduction

I chose this project because often times I have had to handle Docker images in the past and it's good practice to know how to put this in an Amazon Docker repository. However, little did I know that behind this project another project was hiding.

## Use Case

The use case for this is hosting your own Docker images on aws rather than on Dockerhub. The reason why you would do this is to have a private repo but also to host custom Docker images.

## Cloud Research

- The first mistake I made was not realizing that I had to have Docker set up on my computer, but also an IAM user or having some sort of means of authenticating me before pushing anything to ECR.
- The main part of this exercise was setting up the IAM user. Once I got it set up though, it worked out just fine!
- I don't know why the `getting-started` Docker image demo does not work locally. Is it because I'm on Apple Silicon or is there a misconfiguration somewhere?

# Next Steps

Setting up a Kubernetes deployment or more on IAM user management.
