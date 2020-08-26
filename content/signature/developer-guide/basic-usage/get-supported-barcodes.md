---
id: "get-supported-barcodes"
url: "signature/get-supported-barcodes"
title: "Get Supported Barcodes"
productName: "GroupDocs.Signature Cloud"
weight: 2
description: ""
keywords: ""
---

# Supported Barcode Types #

GroupDocs.Signature Cloud REST API supports to sign a document with Barcode. This API lists all supported Barcode types.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in example [to list supported Barcode types](https://apireference.groupdocs.cloud/signature/#/Info/GetSupportedBarcodes).

## cURL Example ##

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}} {{< tab tabNum="1" >}}

```javascript
 curl -X GET "https://api.groupdocs.cloud/v2.0/signature/barcodes" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
```

{{< /tab >}} {{< tab tabNum="2" >}}

```javascript
{
  "barcodeTypes": [
    {
      "name": "AustralianPosteParcel"
    },
    {
      "name": "AustralianPost"
    },
    {
      "name": "Codabar"
    },
    {
      "name": "CodablockF"
    },
    {
      "name": "Code11"
    },
    {
      "name": "Code128"
    },
    {
      "name": "Code16K"
    },
    {
      "name": "Code32"
    },
    {
      "name": "Code39Standard"
    },
    {
      "name": "Code39Extended"
    },
    {
      "name": "Code93Extended"
    },
    {
      "name": "Code93Standard"
    },
    {
      "name": "DatabarExpanded"
    },
    {
      "name": "DatabarExpandedStacked"
    },
    {
      "name": "DatabarLimited"
    },
    {
      "name": "DatabarOmniDirectional"
    },
    {
      "name": "DatabarStacked"
    },
    {
      "name": "DatabarStackedOmniDirectional"
    },
    {
      "name": "DatabarTruncated"
    },
    {
      "name": "DataLogic2of5"
    },
    {
      "name": "DeutschePostIdentcode"
    },
    {
      "name": "DeutschePostLeitcode"
    },
    {
      "name": "DotCode"
    },
    {
      "name": "DutchKIX"
    },
    {
      "name": "EAN8"
    },
    {
      "name": "EAN13"
    },
    {
      "name": "EAN14"
    },
    {
      "name": "GS1CodablockF"
    },
    {
      "name": "GS1Code128"
    },
    {
      "name": "IATA2of5"
    },
    {
      "name": "Interleaved2of5"
    },
    {
      "name": "ISBN"
    },
    {
      "name": "ISMN"
    },
    {
      "name": "ISSN"
    },
    {
      "name": "ItalianPost25"
    },
    {
      "name": "ITF14"
    },
    {
      "name": "ITF6"
    },
    {
      "name": "MacroPdf417"
    },
    {
      "name": "Matrix2of5"
    },
    {
      "name": "MaxiCode"
    },
    {
      "name": "MicroPdf417"
    },
    {
      "name": "MSI"
    },
    {
      "name": "OneCode"
    },
    {
      "name": "OPC"
    },
    {
      "name": "PatchCode"
    },
    {
      "name": "Pdf417"
    },
    {
      "name": "Pharmacode"
    },
    {
      "name": "Planet"
    },
    {
      "name": "Postnet"
    },
    {
      "name": "PZN"
    },
    {
      "name": "RM4SCC"
    },
    {
      "name": "SCC14"
    },
    {
      "name": "SingaporePost"
    },
    {
      "name": "SSCC18"
    },
    {
      "name": "Standard2of5"
    },
    {
      "name": "SwissPostParcel"
    },
    {
      "name": "UPCA"
    },
    {
      "name": "UpcaGs1Code128Coupon"
    },
    {
      "name": "UpcaGs1DatabarCoupon"
    },
    {
      "name": "UPCE"
    },
    {
      "name": "VIN"
    }
  ]
}
{{< /tab >}} {{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Get Supported Barcodes List ###

{{< tabs tabTotal="6" tabID="10" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Python" tabName6="Ruby" >}} {{< tab tabNum="1" >}}

{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Get_Supported_Barcodes.cs >}}

{{< /tab >}} {{< tab tabNum="2" >}}

{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Get_Supported_Barcodes.java >}}

{{< /tab >}} {{< tab tabNum="3" >}}

{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Get_Supported_Barcodes.php >}}

{{< /tab >}} {{< tab tabNum="6" >}}

{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Get_Supported_Barcodes.rb >}}

{{< /tab >}} {{< tab tabNum="4" >}}

{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Get_Supported_Barcodes.js >}}

{{< /tab >}} {{< tab tabNum="5" >}}

{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Get_Supported_Barcodes.py >}}

{{< /tab >}} {{< /tabs >}}
