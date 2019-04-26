---
layout: post
title: The New Hub
---

I have been using AWS for 3 years and, from the very beginning, I was blown away with how easy it was to build meaningful content and then release it to reach thousands of people. My first foray was the Alexa Skill, [Interview Prep](https://www.amazon.com/Alexander-King-Interview-Prep/dp/B01LW7L2VD){:target="_blank"}. I had finally decided that I wanted to leave my job and realized that I needed to level up my online code presence. After a little more than a week of figuring out how to use the AWS CLI and how to wire everything up to make an Alexa Skill, I [open-sourced](https://github.com/apsking/InterviewPrepAlexaSkill){:target="_blank"} the content and got my first skill published. Its value was minimal - during my technical interview preparation, I found myself scouring the internet for ideas and tips on how to make sure I was ready. The skill takes that information and gives the user a voice experience to keep their interviewing skills sharp (Try it! "Alexa, open interview prep")! A few weeks later, I made it through an interview loop at Amazon Alexa, citing that project as evidence of my skills and drive. I accepted their job offer. Score!

I caught the Alexa Skill bug and was fascinated that I could write software in such a new space and that people actually wanted to use it. This led me to my next Alexa Skill hosted on AWS, [My Pet Rock](https://www.amazon.com/Alexander-King-My-Pet-Rock/dp/B073VDPTCW){:target="_blank"}. I poured a few months into its development, release, and upkeep. Today, it is still my most popular skill and is used by thousands of people every day ("Alexa, open My Pet Rock"). This did, however, teach me how important resource management within AWS was. I didn't know how to use AWS CloudFormation at the time, so it is all hand-jammed into the AWS Console and now proves painful to iterate on.

This all brings me to the CloudFormation and the [AWS CDK (Cloud Development Kit)](https://github.com/awslabs/aws-cdk){:target="_blank"}. I switched teams at Amazon and began to use CloudFormation much more often and really fell in love with how one could manage resources in code. While CloudFormation gives you the tools to CRUD your resources, it doesn't give you the ability to re-use things that you have designed. Say you need to create a dashboard to track your common metrics:

~~~
Resources:
  Dashboard:
      Type: "AWS::CloudWatch::Dashboard"
      Properties:
          DashboardName: "Monitor all the Things"
          DashboardBody: //All my gross JSON for a CloudWatch dashboard

~~~

Doing it once is pretty straightforward. Toss in some `.yaml`, mix it in with some CloudWatch `.json` that you basically copied from the Console anyway, build the CloudFormation template, and bam! You have a dashboard. However, the problem comes when you realize that you want to replicate that Dashboard for every one of your projects that use a similar pattern.

Behold the AWS CDK! It uses declarative code to build and manage your AWS infrastructure. You can use this code to build re-useable components just like you would when you write logical software. I am really psyched about the potential that the CDK has to transform how everyone builds on AWS.

I created this site to give others insights into how the CDK can change how you build on AWS, to explore the nuances of its implementation, and keep up on all of its latest and greatest! Enjoy!
