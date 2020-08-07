---
id: "searchresult"
url: "signature/searchresult"
title: "SearchResult"
productName: "GroupDocs.Signature Cloud"
weight: 9
description: ""
keywords: ""
---

SearchResult data structure returned by Search API method as output result

##### SearchResult example #####

```javascript
{
  "fileInfo": {
    "filePath": "/words/docx/one-page.docx",
    "password" : "1234567890"
  },
  "size" : 12345,
  "signatures": [
    {
      "barcodeType": "Code128",
      "text": "123456789012",
      "format": "Portable Network Graphic",
      "signatureType": "Barcode",
      "pageNumber": 1,
      "signatureId": "114bc076-f734-4edf-9ce4-2277725a6ea5",
      "isSignature": true,
      "createdOn": "2020-07-22T07:45:01.6812929+00:00",
      "modifiedOn": "2020-07-22T07:45:01.6812929+00:00",
      "top": 100,
      "left": 100,
      "width": 300,
      "height": 100
    }
  ]
}
```

##### SignResult fields #####

|Name|Description
|---|---
|FilePath|Name of the verified document
|Size|Size of the verified document
|IsSuccess|Result of verification process
|Signatures|Array of found Signatures that match for passed Search Options.

Based of found signature type of one the following data structures will be created

BarcodeSignature

DigitalSignature

ImageSignature

QRCodeSignature

TextSignature
