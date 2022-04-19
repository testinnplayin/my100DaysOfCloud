# Billing and budgets oh my!

## Introduction

This is the continuation of the billing alarm project I worked on yesterday. I think it's super important to not push this subject to just a small detail, even though it's definitely not the most exciting subject in the world.

Since we do things for our clients, and persumably there's a reason why we're doing this in the first place, we need to at some point think about money. This means thinking about budgets, billing and uncool stuff like that.

The cloud is supposed to be about flexibilty. If you don't get the very basics down pat for helping out your client, you could end up costing them more money (and yourself, while at it). Setting up the budget is super important.

## Prerequisite

Knowing how to set up billing so that an IAM user can access that part of aws is helpful. I didn't know this and as a result lost time. The documentation is not super clear on what button must be clicked on to edit the settings, so I missed it at first.

Knowing a bit about billing in other contexts is also helpful, especially the way a company handles bills. Ultimately, you'll probably be handling billing for a company, whether your own or your client's so ...

Having an IAM user is also helpful.

## Use Case

- This is fairly simple, so I don't think we need to show a diagram for this part. You fix a budget in order to be able to have a better handle on what you actually pay Amazon and when. Not only does this help having control on your expenditures but also generates information that can serve as the basis of following your costs.
- For a company, this is essential, but you can also couple CloudWatch, which we saw yesterday, SNS topics and alerts with the budget alert system. You can set the alerts up with SNS or use the Amazon chatbot. Either way, you can be notified of when you'll be billed, what the budget is like and what you will be billed.
- You can set up actions in order to be warned if you are about to go over the budget, much like with billing alerts. You'll have a better idea of what's going on financially with aws and either plan for it or find some way to reduce the costs.
- If you absolutely want to use the Cost Explorer functionality and you only just set up your IAM user at the same time with billing access as starting this project, you're out of luck. Amazon can take up to 24 hours to put that in place. You can still create a budget, just not one that uses that feature.

## Cloud Research

- My trials started with setting up the IAM user I already made a few days ago with being able to look at the billing and budget part. I quite cleverly set up the policy for the user group I wanted but still could not see the billing. This is because I had ommitted going into my account settings as root to enable IAM user access to billing.
- I did not finalize the budget since I was mocking paying Amazon 100 USD/month and obviously I don't want to be charged anything! However, I did go through all the steps except for the final submission.
- I learned how cool it is to couple this with SNS alerts. It's fairly easy to set up an alert system. After futzing with a custom alertmanager in a Prometheus stack deployment, this was super simple to put in place by comparison.
- I was also impressed by how fine-grained you can set up what goes into the budget itself and the other thresholds and alerting you can put in place.
- It is better to use the root account for as little as possible, so it's a best practice to set up at least one IAM user who can perform billing and/or budget actions.

## Try yourself

I already had an IAM user on hand when I started this quest.
### Step 1 — Create an IAM user if needed

Go to the IAM service of aws and create an administrator account while on your root account. I won't go into too many more details than this because I already had an IAM user.

### Step 2 — Enable billing access for IAM users on account

Be sure to go into the account settings while still on as root user. Go to the billing section, click on small 'Edit' link near the title of the section and click on Enable IAM users billing access.

### Step 3 — Add billing and budget policy for IAM users

In the IAM service, add a policy, name it something like `billing-budget-access` and provide billing and budget access. For example, I allowed IAM user read access to billing and read/write access to budgets, and not much else.

The actions in question are under `Billing` and `Budget` in the actions dropdowns. They both have to be added as separate permissions to the policy.

Add the policy in the permissions part of either the IAM user or the IAM user group you want associated with this policy.

### Step 4 - Set up budget


Determine first what kind of budget you want. I chose `Cost` because I want to pay Amazon what I use.

Log out as root user and log in as an IAM user that has access to billing/budgets. Navigate to the `Budget` tab of the [Cost Management console](https://console.aws.amazon.com/cost-management/home) and click on `Create Budget`. Then select `Cost`.

Set the amount you want to pay and whether you want it to be recurrent or not. I selected recurrent for `100 USD` a month.

Then you can choose to select actions, such as alerting someone via email when you have gone over a certain amount. I set `5%` and `over amount`. You can choose to include or exclude certain kinds of costs, like credits or taxes for example.

In alerts (optional), I set up a new SNS topic by clicking on `New topic`, which took me to a new tab where I could configure a new SNS topic. Once it was set up, I copied the origin of the topic and pasted it in the text box in the budget page.

Then I put in my IAM user's email address. You can put up to 10 different email addresses for the same alert.

I then clicked on `Next`. This takes you to the review page before you finalize the creation of the budget. I did not go further because I don't currently want to be charged money at the moment for aws, since this is just for learning the cloud on aws.

## ☁️ Cloud Outcome

I learned quite a bit. Even though it's not super difficult to set up something in aws, there is a lot of detail and you can probably spend a lot of time optimizing everything. Maybe someone could make a management/simulation game based on aws cloud... for those of us that like that kind of game. I could just see it now: a Steam, indie game...

## Next Steps

I might start looking into the Amazon equivalent of GKE or look at lambdas.
