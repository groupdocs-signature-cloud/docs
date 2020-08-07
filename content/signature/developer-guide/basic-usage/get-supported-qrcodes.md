---
id: "get-supported-qrcodes"
url: "signature/get-supported-qrcodes"
title: "Get Supported QRCodes"
productName: "GroupDocs.Signature Cloud"
weight: 3
description: ""
keywords: ""
---

# Supported QR-Codes Types #

GroupDocs.Signature Cloud REST API supports to sign a document with QR-Code. You can list all supported QR-Ccode types using this API.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to list supported QR-Code types](https://apireference.groupdocs.cloud/signature/#/Info/GetSupportedQRCodes).

## cURL Example ##

Request

```html
curl -X GET "https://api.groupdocs.cloud/v2.0/signature/qrcodes" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
 ```

 Response

```html
{
  "qrCodeTypes": [
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

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Get Supported QR-Codes List ###

C#

{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Get_Supported_QRCodes.cs >}}

Java

{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Get_Supported_QRCodes.java >}}

PHP

{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Get_Supported_QRCodes.php >}}

Ruby

{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Get_Supported_QRCodes.rb >}}

Node

{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Get_Supported_QRCodes.js >}}

Python

{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Get_Supported_QRCodes.py >}}
