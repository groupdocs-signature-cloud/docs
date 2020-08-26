---
id: "get-supported-qrcodes"
url: "signature/get-supported-qrcodes"
title: "Get Supported QRCodes"
productName: "GroupDocs.Signature Cloud"
weight: 3
description: ""
keywords: ""
---

GroupDocs.Signature Cloud REST API supports to sign a document with QR-Code. You can list all supported QR-Ccode types using this API.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to list supported QR-Code types](https://apireference.groupdocs.cloud/signature/#/Info/GetSupportedQRCodes).

## cURL Example ##

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}} {{< tab tabNum="1" >}}

```javascript
curl -X GET "https://api.groupdocs.cloud/v2.0/signature/qrcodes" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
```

{{< /tab >}} {{< tab tabNum="2" >}}

```javascript
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
{{< /tab >}} {{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Get Supported QR-Codes List ###

{{< tabs tabTotal="6" tabID="10" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Python" tabName6="Ruby" >}} {{< tab tabNum="1" >}}

{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Get_Supported_QRCodes.cs >}}

{{< /tab >}} {{< tab tabNum="2" >}}

{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Get_Supported_QRCodes.java >}}

{{< /tab >}} {{< tab tabNum="3" >}}

{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Get_Supported_QRCodes.php >}}

{{< /tab >}} {{< tab tabNum="6" >}}

{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Get_Supported_QRCodes.rb >}}

{{< /tab >}} {{< tab tabNum="4" >}}

{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Get_Supported_QRCodes.js >}}

{{< /tab >}} {{< tab tabNum="5" >}}

{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Get_Supported_QRCodes.py >}}

{{< /tab >}} {{< /tabs >}}
