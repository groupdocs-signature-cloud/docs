---
id: "working-with-document-information"
url: "signature/working-with-document-information"
title: "Working with Document Information"
productName: "GroupDocs.Signature Cloud"
weight: 14
description: ""
keywords: ""
---

## File Formats API ##

This API intended for getting all supported file formats by GroupDocs.Signature Cloud.

#### URI ####

```html 

~/formats

 ```

#### HTTP GET ####

#### Example 1 (Get all supported file formats) ####

Retrieves list of supported file formats.

###### Example URL ######

```html 

https://api.groupdocs.cloud/v2.0/signature/formats

 ```

###### Example Response ######

```html 

{
  "formats": [
    {
      "extension": ".pdf",
      "fileFormat": "Portable Document Format"
    },
    {
      "extension": ".doc",
      "fileFormat": "Microsoft Word"
    },
    {
      "extension": ".docx",
      "fileFormat": "Microsoft Word"
    },
...
  ]
}

 ```

## Barcode formats API ##

This API intended for getting all supported barcode types by GroupDocs.Signature Cloud.

#### URI ####

```html 

~/barcodes

 ```

#### HTTP GET ####

#### Example 2 (Get all supported barcode types) ####

Retrieves list of supported barcode types.

###### Example URL ######

```html 

https://api.groupdocs.cloud/v2.0/signature/barcodes

 ```

###### Example Response ######

```html 

{
  "barcodeTypes": [    
    {
      "name": "Code11"
    },
    {
      "name": "Code128"
    },
    ....
    {
      "name": "EAN14"
    }
  ]
}

 ```

## QRCode formats API ##

This API intended for getting all supported qr-code types by GroupDocs.Signature Cloud.

#### URI ####

```html 

~/qrcodes

 ```

#### HTTP GET ####

#### Example 3 (Get all supported qr-code types) ####

Retrieves list of supported qr-code types.

###### Example URL ######

```html 

https://api.groupdocs.cloud/v2.0/signature/qrcodes

 ```

###### Example Response ######

```html 

{
  "qrCodeTypes": 
  [
    {
      "name": "Aztec"
    },
    {
      "name": "DataMatrix"
    },
    {
      "name": "GS1DataMatrix"
    },
    {
      "name": "GS1QR"
    },
    {
      "name": "QR"
    }
  ]
}

 ```

## Document Information API ##

This API intended for getting information about the document: pages, etc.

#### URI ####

```html 

~/info

 ```

#### HTTP POST ####

#### Example 4 (Get document information) ####

Takes [InfoSettings ]({{< ref "signature/developer-guide/data-structures/infosettings.md" >}}))as input and returns [InfoResult]({{< ref "signature/developer-guide/data-structures/inforesult.md" >}})) 

###### Example URL ######

```html 

https://api.groupdocs.cloud/v2.0/signature/info

 ```

###### Example Request  ######

```html 

{
  "FileInfo": {
    "FilePath": "/words/docx/one-page.docx"
  }  
}

 ```

###### Example Response ######

```html 

{
  "pages": [
    {
      "number": 1,
      "width": 612,
      "height": 792
    }
  ]
}

 ```