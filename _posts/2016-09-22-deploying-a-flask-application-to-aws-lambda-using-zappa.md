---
layout: post
published: true
mathjax: false
featured: false
comments: false
title: Deploying a Flask application to AWS Lambda using Zappa
description: ''
headline: ''
modified: ''
categories: ''
tags: ''
imagefeature: ''
---
AWS Lambda lets you run code without provisioning or managing servers. The advantage of using Lamdba is: **zero administration**. Just upload your code and Lambda takes care of everything required to run and scale your code with high availability. So how does one deploy a flask application to AWS Lamdba.

### Enter Zappa
From their github site: "Zappa makes it super easy to deploy all Python WSGI applications on AWS Lambda + API Gateway. Think of it as "serverless" web hosting for your Python web apps. That means infinite scaling, zero downtime, zero maintenance - and at a fraction of the cost of your current deployments!"

So let's get started:

1) Go to the directory containing the flask code.

2) Setup your virtual env
```
$ pip install virtualenv                     ###only if you dont have virtualenv already installed
$ virtualenv env
$ source env/bin/activate
$ pip install flask zappa
```
This will create a zappa_setting.json file which should look something like the one below. Make sure the s3_bucket matches the one you have access to. Dev stands for your dev environment, you can have as many configurations as you like.

```
{ "dev": {
        "s3_bucket": "your_s3_bucket",
        "app_function": "my_app.app";
    }
}
```

3) Install AWS CLI and enter your access key and secret access key. These can be obtained via the AWS console. Create one if you dont have one already.
```
$ pip install awscli
$ aws configure
```

4) Run
```
$ zappa deploy dev
That's it. Your app should be running on AWS Lambda!
```
