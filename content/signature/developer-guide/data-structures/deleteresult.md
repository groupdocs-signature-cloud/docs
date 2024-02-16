---
id: "deleteresult"
url: "signature/deleteresult"
title: "DeleteResult"
productName: "GroupDocs.Signature Cloud"
weight: 13
description: ""
keywords: ""
toc: True
---

DeleteResult data structure returned by Delete API method as output result

##### DeleteResult example

```javascript
{
  "fileInfo": {
    "filePath": "signedBarcode_one-page.docx",
    "storageName": null,
    "versionId": null,
    "password": null
  },
  "size": 1360026,
  "succeeded": [
    {
      "barcodeType": "Code128",
      "text": "123456789012",
      "format": null,
      "signatureType": "Barcode",
      "pageNumber": 1,
      "signatureId": "4cb67aa8-835d-4877-8a5d-5a9ad015a098",
      "isSignature": true,
      "createdOn": "2020-07-23T07:26:42.7549544+00:00",
      "modifiedOn": "2020-07-23T07:36:03.9037414+00:00",
      "top": 0,
      "left": 0,
      "width": 0,
      "height": 0
    }
  ],
  "failed": []
}

```

##### DeleteResult fields

|Name|Description|API Version
|---|---|---
|fileInfo|Input file information|
|size|The size of the output document|
|Succeeded|List of successfully deleted signatures|
|Failed|List of signatures that were not deleted|
