AWS Static Website

A secure, globally distributed static portfolio website deployed on AWS using Amazon S3 and Amazon CloudFront.

#Project Overview

This project demonstrates the deployment of a static website using AWS cloud infrastructure with a focus on security, HTTPS, performance, and cost awareness.

The website files are stored in a private Amazon S3 bucket and delivered to users through Amazon CloudFront.

 #Architecture

                    Internet
                       │
                       ▼
              ┌─────────────────┐
              │   CloudFront    │
              │   HTTPS + CDN   |
              └────────┬────────┘
                       │
                       │ Origin Access Control
                       ▼
              ┌─────────────────┐
              │       S3        |
              │ Private Bucket  │
              └─────────────────┘

# AWS Services Used

Amazon S3

Used to store the static website files:

- "index.html"
- "style.css"

The S3 bucket is configured with Block Public Access enabled, preventing direct public access to the website files in the bucket.

Amazon CloudFront

CloudFront is used as the content delivery network (CDN).

It provides:

- Global content delivery
- HTTPS access
- Caching
- Improved performance
- Secure access to the private S3 origin

CloudFront Origin Access Control (OAC)

Origin Access Control allows CloudFront to securely access objects stored in the private S3 bucket.

The S3 bucket does not need to be publicly accessible.

AWS Budgets

An AWS monthly budget was configured to monitor account spending and provide an email alert if costs reach the configured threshold.

#Security Configuration

The following security controls were implemented:

- S3 Block Public Access enabled
- S3 bucket kept private
- CloudFront Origin Access Control enabled
- HTTPS enabled through CloudFront
- No direct public access to the S3 objects
- AWS Budget alert configured for cost monitoring

#Security Verification

The deployment was tested to confirm that the S3 bucket could not be accessed directly.

Direct S3 Access

Attempting to access the S3 object directly resulted in:

XML Access Denied

This confirmed that the S3 bucket was not publicly accessible.

CloudFront Access

The website successfully loaded through the CloudFront distribution.

This confirmed that CloudFront could retrieve the private S3 objects through Origin Access Control.

HTTPS Verification

The CloudFront website was accessed using HTTPS and the browser confirmed that the connection was secure.

#Cost Considerations

This project was designed to keep AWS usage low.

No EC2 instance was required because the website is completely static.

AWS WAF was also not enabled for this project.

An AWS Budget was configured to monitor account spending and provide an alert if the configured monthly threshold is reached.

Actual AWS costs can vary depending on traffic, storage, data transfer, and account-specific pricing.

#Project Structure

aws-static-website/
│
├── index.html
├── style.css
└── README.md

🎯 Skills Demonstrated

- Amazon S3
- Amazon CloudFront
- CloudFront Origin Access Control
- HTTPS
- S3 security configuration
- AWS cost monitoring
- Static website deployment
- Basic cloud architecture
- AWS security best practices

 #What I Learned

Through this project, I gained practical experience with:

1. Creating and configuring an Amazon S3 bucket
2. Uploading and managing website assets
3. Keeping an S3 bucket private
4. Creating a CloudFront distribution
5. Configuring Origin Access Control
6. Serving private S3 content through CloudFront
7. Verifying HTTPS
8. Testing cloud security controls
9. Monitoring AWS spending with AWS Budgets

#Future Improvements

Possible future improvements include:

- Custom domain with Route 53
- AWS Certificate Manager custom TLS certificate
- AWS WAF protection
- CloudFront access logging
- CI/CD deployment using GitHub Actions
- Automated infrastructure deployment using AWS CDK

#Live Website

CloudFront:
https://d1h5atmiiic05v.cloudfront.net

#Author

Abdulbaqi Abayomi Shatta

AWS Cloud & Cybersecurity enthusiast focused on building practical cloud infrastructure and security projects.

##Screenshots
### S3 Block Public Access
![S3 Block Public Access]
(screenshots/s3-block-public-access.png)

### CloudFront Distribution
![CloudFront Distribution]
(screenshots/cloudfront-distribution.png)

### HTTPS Website
![CloudFront HTTPS Website]
(screenshots/cloudfront-ecure-web-confirmed-https.png)

### Budget Consumption Setup
![Budget Consumption Setup]
(screenshots/budget-setup.png)
