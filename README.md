# AWS Serverless Document Processing Architecture

A production-ready AWS serverless architecture for automated document and receipt text extraction with secure storage and notification workflows.

---

## Overview

This repository presents a scalable, event-driven serverless architecture designed to automate document ingestion, AI-based text extraction, structured data storage, and email notifications — without managing infrastructure.

The solution follows AWS Well-Architected principles and is designed for cost efficiency, security, and operational scalability.

---

## Architecture Diagram

![AWS Architecture Diagram](Automated%20Receipt%20Processing%20Tool%20Architecture.drawio.png)

---

## Architecture Summary

### Purpose

Automate document and receipt processing using AWS-native services while maintaining security, scalability, and low operational overhead.

### Core Workflow

1. User uploads document to Amazon S3  
2. S3 triggers AWS Lambda  
3. Lambda invokes Amazon Textract for AI-based text extraction  
4. Extracted data is stored in Amazon DynamoDB  
5. Amazon SES sends completion notification  

---

## AWS Services Used

- **Amazon S3** – Secure document storage and event trigger
- **AWS Lambda** – Serverless orchestration layer
- **Amazon Textract** – AI-powered structured and unstructured text extraction
- **Amazon DynamoDB** – Low-latency structured data storage
- **Amazon SES** – Email notification service
- **AWS IAM** – Least-privilege access control enforcement

---

## Key Architectural Benefits

- **Fully Serverless** – No infrastructure management required  
- **Event-Driven** – Automatically scales with workload  
- **Cost-Efficient** – Pay-per-use pricing model  
- **Secure by Design** – Role-based IAM access control  
- **Highly Available** – Built using managed AWS services  

---

## Production Considerations

- CloudWatch logging and monitoring configured for Lambda execution visibility  
- S3 bucket policies restrict public access and enforce private object storage  
- IAM roles configured using least-privilege principles  
- Encryption at rest enabled for S3 and DynamoDB  
- Designed for horizontal scaling via event-driven architecture  
- Can be deployed within isolated VPC environments if required for compliance  

---

## Cost Model Overview

This architecture follows a consumption-based pricing structure:

- AWS Lambda billed per execution duration  
- Amazon Textract billed per page processed  
- DynamoDB configured with on-demand capacity mode  
- No EC2 or persistent compute infrastructure required  

This makes the design suitable for low-to-moderate document workloads without fixed infrastructure costs.

---

## Use Cases

- FinTech invoice and receipt automation  
- EdTech document processing workflows  
- Insurance claims digitisation  
- Internal enterprise document routing  
- SaaS backend document processing services  

---

## How to Edit the Architecture Diagram

- Editable source:  
  `Automated Receipt Processing Tool Architecture.drawio`

- Open using:
  - https://app.diagrams.net/
  - https://diagrams.net/

The PNG file includes embedded diagram data and can be re-imported into diagrams.net.

---

## Author

Mohammed Bakare  
AWS Certified Cloud Practitioner  
LinkedIn: https://www.linkedin.com/in/mohammed-bakare-94a655288
---
---

## ❤️ Support

If this architecture or documentation has been useful, you can support ongoing work via GitHub Sponsors:
https://github.com/sponsors/Deeplomatcode

