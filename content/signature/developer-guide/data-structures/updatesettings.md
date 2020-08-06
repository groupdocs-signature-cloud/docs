---
id: "updatesettings"
url: "signature/updatesettings"
title: "UpdateSettings"
productName: "GroupDocs.Signature Cloud"
weight: 10
description: ""
keywords: ""
---

# UpdateSettings #

UpdateSettings data structure used as input parameters of Update API method.


##### UpdateSettings example #####

```html 

{
  'FileInfo': {
    'FilePath': 'signedBarcode_one-page.docx'
  },
  'Options': [
    {      
      'SignatureType': 'Barcode',
      'SignatureId': '4cb67aa8-835d-4877-8a5d-5a9ad015a098',
      'Left': 200,
      'Top': 200,
      'Width': 300,
      'Height': 100,
      'IsSignature': true
    }
  ]
}

 ```

##### UpdateSettings fields #####



|#Name|#Description|#API Version
|FileInfo.FilePath|The path of the document, located in the storage. **Required.**| 
|FileInfo.StorageName|Storage name| 
|FileInfo.VersionId|File version Id| 
|FileInfo.Password|Password for password-protected document to be signed.| 
|Options|Array of options to perform signatures update| 

 
