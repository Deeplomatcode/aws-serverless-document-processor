# aws-serverless-document-processor
AWS Serverless architecture for automated document processing
# AWS Serverless Automated Receipt Processing Tool Architecture

This repository contains an AWS serverless architecture diagram for automated document/receipt text extraction and notifications.

## Architecture Overview
![AWS Architecture Diagram](Automated%20Receipt%20Processing%20Tool%20Architecture.drawio.png)

## Architecture Summary

**Purpose**  
Automates receipt/document text extraction and notifications without managing infrastructure.

**Components**  
- **Amazon S3** – Securely stores uploaded documents; triggers processing events  
- **AWS Lambda** – Orchestrates Textract, DynamoDB, and SES calls  
- **Amazon Textract** – AI-powered text extraction from structured and unstructured documents  
- **Amazon DynamoDB** – Low-latency storage of extracted results  
- **Amazon SES** – Sends user notifications upon completion  
- **AWS IAM** – Defines and enforces secure access permissions for all services and users  

**Key Benefits**  
- **Scalable** – Automatically adapts to workload  
- **Cost-Optimized** – Pay only for actual usage  
- **Resilient** – High availability with no single point of failure  
- **Secure** – Role-based access controls with least-privilege permissions  
- **Serverless** – No infrastructure to manage  

## How to View & Edit the Diagram

- **Editable source**: [`Automated Receipt Processing Tool Architecture.drawio`](Automated%20Receipt%20Processing%20Tool%20Architecture.drawio)  
- To edit, open `.drawio` file in [draw.io](https://app.diagrams.net/) or [diagrams.net](https://app.diagrams.net/).  
- You can also re-import the `.png` into draw.io because it was exported with the embedded diagram data.

## Use Cases
- Automated invoice/receipt processing  
- Document classification and data extraction workflows  
- Email-triggered document processing pipelines

## Credits
Project designed by **Mohammed Bakare**.  
Inspired by AWS Well-Architected best practices and content from **@David Heys**, **@Kim Brooks**, and **@Lucy Wang (@techwithlucy)**.

---

