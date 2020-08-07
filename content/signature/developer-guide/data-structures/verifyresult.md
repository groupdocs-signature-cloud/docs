---
id: "verifyresult"
url: "signature/verifyresult"
title: "VerifyResult"
productName: "GroupDocs.Signature Cloud"
weight: 7
description: ""
keywords: ""
---

VerifyResult data structure returned by Verify API method  as output result

##### VerifyResult example #####

```javascript
{
  "FileInfo": {
    "FilePath": "/words/docx/one-page.docx",
    "Password" : "1234567890"
  },
  "Size" : 12345,
  "IsSuccess": "true"
}

```

##### SignResult fields #####

|Name|Description
|---|---
|FilePath|Name of the verified document
|Size|Size of the verified document
|IsSuccess|Result of verification process
