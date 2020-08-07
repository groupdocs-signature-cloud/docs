---
id: "signresult"
url: "signature/signresult"
title: "SignResult"
productName: "GroupDocs.Signature Cloud"
weight: 5
description: ""
keywords: ""
---

SignResult data structure returned by Sign API method  as output result

##### SignResult example #####

```javascript
{
  "FileInfo": {
    "FilePath": "signed/one-page.pdf",
    "Password" : "1234567890"
  },
  "Size" : 12345,
  "DownloadUrl": "signed/one-page.pdf",
  "succeeded": [
    {
      "qrCodeType": "Aztec",
      "text": "123456789012",
      "format": "Portable Network Graphic",
      "signatureType": "QRCode",
      "pageNumber": 1,
      "signatureId": "bb9ca1b7-fea4-4ec3-9984-9c9279bda16d",
      "isSignature": true,
      "createdOn": "2020-07-21T09:08:25.3947498+00:00",
      "modifiedOn": "2020-07-21T09:08:25.3947498+00:00",
      "top": 100,
      "left": 100,
      "width": 100,
      "height": 100
    }
  ],
  "failed": []
}

```

##### SignResult fields #####

|Name|Description
|---|---
|FilePath|Name of the signed document
|Size|Size of the signed document
|DownloadUrl|Page file path in the cloud storage. Use this value to download page using
|Succeeded|List of newly created signatures
|Failed|List of signatures that were failed to create
