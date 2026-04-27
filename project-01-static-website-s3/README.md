# Project 01 – Static Website Hosting on AWS (S3 + CloudFront)

## Overview
This project demonstrates how to host a static website on AWS using a **serverless and cost‑optimized architecture**.  
The solution uses **Amazon S3** for static content storage and **Amazon CloudFront** as a global Content Delivery Network (CDN).

The goal of this project is to practice core AWS services and architectural decisions aligned with the **AWS Certified Solutions Architect – Associate (SAA‑C03)** certification.

### AWS Services
- Amazon S3

### Key Design Decisions
- No EC2 instances required (cost optimized)
- S3 provides high durability and availability
- Public access restricted to read-only objects
- CloudFront Configuration root object configured as `index.html` to allow access via the root URL

### Security Considerations
- AWS WAF was not enabled at this stage to keep the architecture simple and cost-effective
- WAF can be added later if protection against common web attacks is required

### Cost
- Fits within AWS Free Tier for learning purposes

### Goal
- Learn how to configure S3 for static website hosting


## Architecture

User requests are served through CloudFront over HTTPS.  
CloudFront retrieves static content from an Amazon S3 bucket configured for static website hosting.

User
  |
  v
Amazon CloudFront (HTTPS, caching, global edge locations)
  |
  v
Amazon S3 (Static Website Hosting)

