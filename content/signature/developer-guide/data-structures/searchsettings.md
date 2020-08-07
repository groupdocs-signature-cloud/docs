---
id: "searchsettings"
url: "signature/searchsettings"
title: "SearchSettings"
productName: "GroupDocs.Signature Cloud"
weight: 8
description: ""
keywords: ""
---

SearchSettings data structure used as input parameters of Search API method.

##### SearchSettings example #####

```javascript
{
  "FileInfo": {
    "FilePath": "string",
    "StorageName": "string",
    "VersionId": "string",
    "Password": "string"
  },
  "Options":
   [
    {
        "SignatureType": "Barcode",  
        "Page": 1,
        "Text": "123",
        "BarcodeType": "Code128",
        "MatchType": "Contains"
    }
   ]
 }
```

##### SearchSettings fields #####

|Name|Description|API Version
|---|---|---
|FileInfo.FilePath|The path of the document, located in the storage. **Required.**|
|FileInfo.StorageName|Storage name|
|FileInfo.VersionId|File version Id|
|FileInfo.Password|Password for password-protected document to be signed.|
|Options|Array with at least one SearchOptions that specifies search options to provide search in the document for different signatures
