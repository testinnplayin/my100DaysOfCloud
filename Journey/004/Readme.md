<!-- This template removes the micro tutorial for a quicker post and removes images for a full template check out the 000-DAY-ARTICLE-LONG-TEMPLATE.MD-->
# Creating an S3 bucket and hosting static server with CloudFront

## Introduction

I have already had to do this in a previous job. The goal at my old workplace was to host a gzipped bundle of static assets on CloudFront and serve them quickly to our customers.

## Use Case

- This is to host static assets in particular in such a way that they arrive super quickly to a user visiting a website.

## Cloud Research

- I managed to get everything setup properly on CloudFront and I thought on S3 as well. Unfortunately, I didn't realize that I couldn't update the S3 bucket with public access once it was made so my website couldn't be visited. Oops!
- I did manage to get an error page working. It was a nicely inaccessible website with a working error page. Yay!

