---
id: "deletesettings"
url: "signature/deletesettings"
title: "DeleteSettings"
productName: "GroupDocs.Signature Cloud"
weight: 12
description: ""
keywords: ""
---

DeleteSettings data structure used as input parameters of Delete API method.

##### DeleteSettings example #####

```javascript
{
  'FileInfo': {
    'FilePath': 'signedBarcode_one-page.docx'
  },
  'Options': [
    {
      'SignatureType': 'Barcode',
      'SignatureId': '4cb67aa8-835d-4877-8a5d-5a9ad015a098'
    }
  ]
}
```

##### UpdateSettings fields #####

|Name|Description|API Version
|---|---|---
|FileInfo.FilePath|The path of the document, located in the storage. **Required.**|
|FileInfo.StorageName|Storage name|
|FileInfo.VersionId|File version Id|
|FileInfo.Password|Password for password-protected document to be signed.|
|Options|Array of options to perform signatures delete|
