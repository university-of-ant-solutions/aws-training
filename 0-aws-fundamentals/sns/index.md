---
description: SNS
keywords: sns, aws
title: SNS
---

### AWS Simple Notification Service – SNS – Certification

![sns aws](pictures/screen-shot-2016-05-06-at-8-13-57-am.png)

- Simple Notification Service – SNS is a web service that coordinates and manages the delivery or sending of messages to subscribing endpoints or clients

- SNS provides the ability to create Topic which is a logical access point and communication channel.

- Each topic has a unique name that identifies the SNS endpoint for publishers to post messages and subscribers to register for notifications.

- Producers and Consumers communicate asynchronously with subscribers by producing and sending a message to a topic

- Producers push messages to the topic, they created or have access to, and SNS matches the topic to a list of subscribers who have subscribed to that topic, and delivers the message to each of those subscribers

- Subscribers receive all messages published to the topics to which they subscribe, and all subscribers to a topic receive the same messages.

- Subscribers (i.e., web servers, email addresses, SQS queues, AWS Lambda functions) consume or receive the message or notification over one of the supported protocols (i.e., SQS, HTTP/S, email, SMS, Lambda) when they are subscribed to the topic.

### Accessing Amazon SNS

- Amazon Management console

  - Amazon Management console is the web-based user interface which can be used to manage SNS

- AWS Command line Interface (CLI)

  - Provides commands for a broad set of AWS products, and is supported on Windows, Mac, and Linux.

- AWS Tools for Windows Powershell

  - Provides commands for a broad set of AWS products for those who script in the PowerShell environment

- AWS SNS Query API

  - Query API allows for requests are HTTP or HTTPS requests that use the HTTP verbs GET or POST and a Query parameter named Action

- AWS SDK libraries

  - AWS provide libraries in various languages which provide basic functions that automate tasks such as cryptographically signing your requests, retrying requests, and handling error responses

### SNS Supported Transport Protocols

- HTTP, HTTPS – Subscribers specify a URL as part of the subscription registration; notifications will be delivered through an HTTP POST to the specified URL.

- Email, Email-JSON – Messages are sent to registered addresses as email. Email-JSON sends notifications as a JSON object, while Email sends text-based email.

- SQS – Users can specify an SQS queue as the endpoint; SNS will enqueue a notification message to the specified queue (which subscribers can then process using SQS APIs such as ReceiveMessage, DeleteMessage, etc.)

- SMS – Messages are sent to registered phone numbers as SMS text messages

### SNS Supported Endpoints

- Email Notifications
  
  - SNS provides the ability to send Email notifications

- Mobile Push Notifications

  - SNS provides an ability to send push notification messages directly to apps on mobile devices. Push notification messages sent to a mobile endpoint can appear in the mobile app as message alerts, badge updates, or even sound alerts

  - Supported push notification services

	  + Amazon Device Messaging (ADM)

    + Apple Push Notification Service (APNS)

    - Google Cloud Messaging (GCM)

    - Windows Push Notification Service (WNS) for Windows 8+ and Windows Phone 8.1+

    - Microsoft Push Notification Service (MPNS) for Windows Phone 7+

    - Baidu Cloud Push for Android devices in China

  - SQS Queues

    - SNS with SQS provides the ability for messages to be delivered to applications that require immediate notification of an event, and also persist in an SQS queue for other applications to process at a later time
    
    - SNS allows applications to send time-critical messages to multiple subscribers through a “push” mechanism, eliminating the need to periodically check or “poll” for updates.

    - SQS can be used by distributed applications to exchange messages through a polling model, and can be used to decouple sending and receiving components, without requiring each component to be concurrently available.

- SMS Notifications

  - SNS provides the ability to send and receive Short Message Service (SMS) notifications to SMS-enabled mobile phones and smart phones

- HTTP/HTTPS Endpoints

  - SNS provides the ability to send notification messages to one or more HTTP or HTTPS endpoints.When you subscribe an endpoint to a topic, you can publish a notification to the topic and Amazon SNS sends an HTTP POST request delivering the contents of the notification to the subscribed endpoint

- Lambda

  - SNS and Lambda are integrated so Lambda functions can be invoked with SNS notifications.

  - When a message is published to an SNS topic that has a Lambda function subscribed to it, the Lambda function is invoked with the payload of the published message

### AWS Certification Exam Practice Questions

```
Questions are collected from Internet and the answers are marked as per my knowledge and understanding (which might differ with yours).

AWS services are updated everyday and both the answers and questions might be outdated soon, so research accordingly.

AWS exam questions are not updated to keep up the pace with AWS updates, so even if the underlying feature has changed the question might not be updated

Open to further feedback, discussion and correction.
```

1. Which of the following notification endpoints or clients does Amazon Simple Notification Service support? Choose 2 answers

**a. Email**

b. CloudFront distribution

c. File Transfer Protocol

**d. Short Message Service**

e. Simple Network Management Protocol

2. What happens when you create a topic on Amazon SNS?

a. The topic is created, and it has the name you specified for it.

b. An ARN (Amazon Resource Name) is created

**c. You can create a topic on Amazon SQS, not on Amazon SNS.**

d. This question doesn’t make sense.

3. A user has deployed an application on his private cloud. The user is using his own monitoring tool. He wants to configure that whenever there is an error, the monitoring tool should notify him via SMS. Which of the below mentioned AWS services will help in this scenario?

a. None because the user infrastructure is in the private cloud/

**b. AWS SNS**

c. AWS SES

d. AWS SMS

4. A user wants to make so that whenever the CPU utilization of the AWS EC2 instance is above 90%, the redlight of his bedroom turns on. Which of the below mentioned AWS services is helpful for this purpose?

a. AWS CloudWatch + AWS SES

**b. AWS CloudWatch + AWS SNS**

c. It is not possible to configure the light with the AWS infrastructure services

d. AWS CloudWatch and a dedicated software turning on the light

5. A user is trying to understand AWS SNS. To which of the below mentioned end points is SNS unable to send a notification?

a. Email JSON

b. HTTP

c. AWS SQS

**d. AWS SES**

6. A user is running a webserver on EC2. The user wants to receive the SMS when the EC2 instance utilization is above the threshold limit. Which AWS services should the user configure in this case?

a. AWS CloudWatch + AWS SES

**b. AWS CloudWatch + AWS SNS**

c. AWS CloudWatch + AWS SQS

d. AWS EC2 + AWS CloudWatch

7. A user is planning to host a mobile game on EC2 which sends notifications to active users on either high score or the addition of new features. The user should get this notification when he is online on his mobile device. Which of the below mentioned AWS services can help achieve this functionality?

**a. AWS Simple Notification Service**

b. AWS Simple Queue Service

c. AWS Mobile Communication Service

d. AWS Simple Email Service

8. You are providing AWS consulting service for a company developing a new mobile application that will be leveraging amazon SNS push for push notifications. In order to send direct notification messages to individual devices each device registration identifier or token needs to be registered with SNS, however the developers are not sure of the best way to do this. You advise them to: –

a. Bulk upload the device tokens contained in a CSV file via the AWS Management Console

b. Let the push notification service (e.g. Amazon Device messaging) handle the registration

c. Implement a token vending service to handle the registration

**d. Call the CreatePlatformEndpoint API function to register multiple device tokens. (Refer [documentation](http://docs.aws.amazon.com/sns/latest/dg/mobile-push-send-devicetoken.html))**

9. A company is running a batch analysis every hour on their main transactional DB running on an RDS MySQL instance to populate their central Data Warehouse running on Redshift. During the execution of the batch their transactional applications are very slow. When the batch completes they need to update the top management dashboard with the new data. The dashboard is produced by another system running on-premises that is currently started when a manually-sent email notifies that an update is required The on-premises system cannot be modified because is managed by another team. How would you optimize this scenario to solve performance issues and automate the process as much as possible?

a. Replace RDS with Redshift for the batch analysis and SNS to notify the on-premises system to update the dashboard

b. Replace RDS with Redshift for the batch analysis and SQS to send a message to the on-premises system to update the dashboard

**c. Create an RDS Read Replica for the batch analysis and SNS to notify me on-premises system to update the dashboard**

d. Create an RDS Read Replica for the batch analysis and SQS to send a message to the on-premises system to update the dashboard.

10. Which of the following are valid SNS delivery transports? Choose 2 answers.

**a. HTTP**

b. UDP

**c. SMS**

d. DynamoDB

e. Named Pipes

11. What is the format of structured notification messages sent by Amazon SNS?

a. An XML object containing MessageId, UnsubscribeURL, Subject, Message and other values

b. An JSON object containing MessageId, DuplicateFlag, Message and other values

c. An XML object containing MessageId, DuplicateFlag, Message and other values

**d. An JSON object containing MessageId, unsubscribeURL, Subject, Message and other values**

12. Which of the following are valid arguments for an SNS Publish request? Choose 3 answers.

**a. TopicAm**

**b. Subject**

c. Destination

d. Format

**e. Message**

f. Language

### Resource

- [http://jayendrapatil.com/aws-sns-simple-notification-service/](http://jayendrapatil.com/aws-sns-simple-notification-service/)

- [Amazon_SNS – Developer Guide](http://docs.aws.amazon.com/sns/latest/dg/welcome.html)
