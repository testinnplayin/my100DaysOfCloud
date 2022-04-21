<!-- This template removes the micro tutorial for a quicker post and removes images for a full template check out the 000-DAY-ARTICLE-LONG-TEMPLATE.MD-->

# Start of my serverless journey

## Introduction

I really like IoT and I really like the cloud. I really, really like the idea of mixing IoT and the cloud.

Even though it's not absolutely necessary to use the cloud or serverless for IoT, I like the idea of having a first layer where IoT devices would talk to a cloud via an edge location, say, for data collection and early processing for example.

Let's say that your company is based in Paris but you have automated greenhouses out in a far away corner of the Île-de-France. You might want to have data collected and treated in an edge location as much as possible. Severless makes this possible, whereas it would be quite a bit harder if you have to place your infrastructure near the greenhouses.

## Use Case

- Here we're starting with a simple adder function. All it does is take a number and another number from an event and add the two numbers together. I went with an idiot simple version where I didn't even check if the inputs were numbers. If I were truly coding something like that, I'd probably have some way of making sure the two inputs are numbers.
- I didn't read the documentation and just played around with the editor a bit. I didn't even code in the Cloud9 IDE I had made. Instead, I just coded the function and tested it directly in the Lambda console.
- Other than not realizing at first that changes made to the code are not saved automatically, this was a fairly simple thing to get up and running.
- I didn't even have to do much with logging. It was already set up with CloudWatch!

## Cloud Research

- I have to ensure saving every time I make a change to the code. I also have to be sure to save tests for reuse.
- Eventually, it would be good to do a more complex function that is hooked up to real events just to see how it works. That might be harder to set up with no big project in place. I'll have to think of something.

## Next Steps

The same but with a Docker image instead. The Lambda function is inside a Docker image.

