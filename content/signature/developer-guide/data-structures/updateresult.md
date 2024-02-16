---
id: "updateresult"
url: "signature/updateresult"
title: "UpdateResult"
productName: "GroupDocs.Signature Cloud"
weight: 2
description: ""
keywords: ""
toc: True
---

UpdateResult data structure returned by Update API method as output result

##### UpdateResult example

```javascript
{
  "fileInfo": {
    "filePath": "signedBarcode_one-page.docx",
    "storageName": null,
    "versionId": null,
    "password": null
  },
  "size": 1360021,
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
      "top": 200,
      "left": 200,
      "width": 300,
      "height": 100
    }
  ],
  "failed": []
}

```

##### UpdateResult fields

|Name|Description|API Version
|---|---|---
|fileInfo|Input file information|
|size|The size of the output document|
|Succeeded|List of successfully modified signatures|
|Failed|List of signatures that were not updated|
