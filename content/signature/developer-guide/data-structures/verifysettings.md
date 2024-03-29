---
id: "verifysettings"
url: "signature/verifysettings"
title: "VerifySettings"
productName: "GroupDocs.Signature Cloud"
weight: 6
description: ""
keywords: ""
toc: True
---

VerifySettings data structure used as input parameters for Verify API method.

##### VerifySettings example

```javascript
{
  "FileInfo": {
    "FilePath": "string",
    "StorageName": "string",
    "VersionId": "string",
    "Password": "string"
  },
  "Options": [
   {
           "SignatureType": "Text",
           "Page": 1,
           "Text": "John",
           "MatchType": "Contains"
        }
  ]
 }

```

##### VerifySettings fields

|Name|Description|API Version
|---|---|---
|FileInfo.FilePath|The path of the document, located in the storage. **Required.**|
|FileInfo.StorageName|Storage name|
|FileInfo.VersionId|File version Id|
|FileInfo.Password|Password for password-protected document to be signed.|
|Options|Array with at least one VerifyOptions that specifies Verification options to provide Document signature verification
