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





 Request

```html 
 curl -X GET "https://api.groupdocs.cloud/v2.0/signature/barcodes" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
 ```




 Response

```html 
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
 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Get Supported Barcodes List ###





 C#




{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Get_Supported_Barcodes.cs >}}







 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Get_Supported_Barcodes.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Get_Supported_Barcodes.php >}}







 Ruby




{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Get_Supported_Barcodes.rb >}}







 Node




{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Get_Supported_Barcodes.js >}}







 Python




{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Get_Supported_Barcodes.py >}}







