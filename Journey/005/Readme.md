<!-- This template removes the micro tutorial for a quicker post and removes images for a full template check out the 000-DAY-ARTICLE-LONG-TEMPLATE.MD-->
# Setting up a billing alarm on aws

## Introduction

I chose billing alarm setup for today's topic due to some experiences at a previous employer. No one knew if we were reaching a threshold or not. I remember clearly seeing a list of services that could have been removed and cost the company less, but no one bothered to do anything about them.

Even though this is more to check if we're not going over a threshold, I think it's still useful to be notified when you are about to go over. There might be things you can do to limit how much cloud you're using or find out why the costs have gone up.

## Use Case

- In order to create a billing alarm, you have to fist go into the billing management part either on root user or on an IAM user you have delegated billing to.
- Once you have gone into this part of aws and selected 'enable billing alarms' on the account, you can then go over to CloudWatch and choose to set up a billing alarm.
- Once you have gone into the wizard to start a billing alarm, you can then choose what thresholds you want to put in place for triggering the alarm.
- If you don't have any aws SNS (simple notification service) topics set up, then the wizard guides you to create a new topic.
- Once you have created one and put the email addresses in the list of people to contact when the alarm triggers, then these people will be emailed with a link to opt in to listening for the alarm.
- By default they will be notified by email. This service is free for up to 10 alarms.

## Cloud Research

- This was not too hard to put into place. The only thing that was not clear was the SNS part because I didn't realize that you have to create a new topic if you don't have one already. I thought there was a default one in place.
