
# 📄 Integrating Amazon Textract into the Serverless Document Processor

## 🔧 Step-by-Step Integration Guide

### 1. Set Up IAM Permissions
Ensure your Lambda function has the necessary permissions to call Amazon Textract. Attach the following policy to your Lambda execution role:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "textract:AnalyzeDocument",
        "textract:DetectDocumentText"
      ],
      "Resource": "*"
    }
  ]
}
```

### 2. Upload Document to S3
Textract works with documents stored in S3. Upload your document (e.g., receipt or invoice) to a designated bucket.

### 3. Invoke Textract from Lambda
Here’s a sample Python snippet using `boto3`:

```python
import boto3

textract = boto3.client('textract')

def extract_text(bucket, document_key):
    response = textract.detect_document_text(
        Document={'S3Object': {'Bucket': bucket, 'Name': document_key}}
    )

    extracted_text = ""
    for item in response["Blocks"]:
        if item["BlockType"] == "LINE":
            extracted_text += item["Text"] + "
"

    return extracted_text
```

### 4. Process Extracted Data
You can store the extracted text in DynamoDB or trigger further processing (e.g., categorization, email notification via SES).

---

## 🧪 Sample Use Case

- **Trigger**: S3 upload event  
- **Lambda**: Extract text using Textract  
- **Store**: Save results in DynamoDB  
- **Notify**: Send email via SES with extracted content

---

## 🛠️ Common Issues & Troubleshooting

| Issue | Solution |
|------|----------|
| `AccessDeniedException` | Check IAM role permissions for Textract and S3 |
| `InvalidS3ObjectException` | Ensure the document exists and is in supported format (PDF, PNG, JPEG) |
| Textract returns empty | Try `AnalyzeDocument` for structured forms or tables |

---

## ✅ Benefits
Enhancing the documentation with this guide will:
- Help users integrate Textract easily
- Reduce troubleshooting time
- Improve adoption of the serverless document processor
