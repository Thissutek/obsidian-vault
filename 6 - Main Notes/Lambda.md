2025-07-11 02:42

Status:

Tag: [[Software Engineering]] [[Cloud Services]] [[AWS]] [[Architecture]]

## Lambda
Run code without managing servers. Think of it as a "functions as a service"

### What it does
example
- you write a function
- you upload it to lambda
- it executes it automatically in response to triggers (HTTP requests, file uploads, DB update, cron jobs)
No server setup, no provisioning, no scaling, all handled by AWS

#### When to use
API's Combine with API Gateway to create RESTful API's
Automation Resize images on S3 Bucket upload, send emails, and cleanup tasks
Cron Jobs Schedule task like daily DB snapshots or reports
Event Processing
Serverless backend
## References 