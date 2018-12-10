
# Api Gateway -> Lambda (Send Email) -> SES (Simple Email Service)

## Description

This is a serverless component consisting of:

- an Api Gateway with a POST `/send` endpoint, that requires three parameters: `toEmails`, `subject`,`message`. It also accepts two optional ones: `ccEmails` and `replyToEmails`.
- a Lambda that sends an email to one or more specified email addresses. Also, depending if the `message` is in a Text or HTML format, it will send it in either of those formats. The `toEmails`,`ccEmails`, and `replyToEmails` parameters must be of Array type.

It's a Nuts & Bolts application component for AWS Serverless Application Repository.

## Deployment Parameters

This component has two CloudFormation deployment parameters:

- `FromEmail`, a required parameter, representing an email from which you want to send an email.
- `CorsOrigin`, an optional parameter, where you can restrict access to only specified domains.

## Latest Release - 1.0.0

Initial release.

## Roadmap - Upcoming changes

Here are the upcoming changes that I'll add to this serverless component:

- ESLint
- Tests