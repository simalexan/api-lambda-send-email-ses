
# AWS Serverless Mailer with ReCaptcha
### Api Gateway -> Lambda (Send Email) -> SES (Simple Email Service)

## Description

This is fork from the excellent work of Alexander Simovic in [api-lambda-send-email-ses]('https://github.com/simalexan/api-lambda-send-email-ses'), for creating a serverless component that sends emails through SES by implenting an API Gateway and a Lambda function. 

Here I've merely extended it to include ReCaptcha, as a common use case for this solution involves a front-end form (such as a contact form in a business page) and a mailer just to notify the webmaster that a request has been received.

Please note this is still a work in progress, and I haven't tested its security.

## Original solution description

- an Api Gateway with a POST `/send` endpoint, that requires three parameters:

  - `toEmails`, Array of strings, that represent all the emails you want to send an email to,
  - `subject`, a string representing the subject of the email
  - `message`, a string representing the message of the email, can be either HTML or regular text
  It also accepts two optional ones: `ccEmails` and `replyToEmails`, both of Array of strings type.

- a Lambda that sends an email to one or more specified email addresses. Also, depending if the `message` is in a Text or HTML format, it will send it in either of those formats. The `toEmails`,`ccEmails`, and `replyToEmails` parameters must be of Array type.

It's a Nuts & Bolts application component for AWS Serverless Application Repository.

## Deployment Parameters

This component has two CloudFormation deployment parameters:

- `FromEmail`, a required parameter, represents the email sender. Must be a SES verified email. If you attempt to send email using a non-verified address or domain, the operation results in an "Email address not verified" error.
- `CorsOrigin`, an optional parameter, where you can restrict access to only specified domains.

## Latest Release 
- TBD

## Roadmap - Upcoming changes

Here are the upcoming changes that I'll add to this serverless component:

- ReCaptcha Integration
- Security Checks
- Documentation
