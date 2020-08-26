---
id: "supported-barcodes"
url: "signature/supported-barcodes"
title: "Supported Barcodes"
productName: "GroupDocs.Signature Cloud"
weight: 5
description: ""
keywords: ""
---

{{< alert style="info" >}}
Note:  The features listed in this page are supported only in GroupDocs.Signature Cloud V1
{{< /alert >}}

GroupDocs.Signature Cloud REST API supports to sign a document with Barcode. This API lists all supported Barcode types.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in example [to list supported Barcode types](https://apireference.groupdocs.cloud/signature/#!/Helper/GetBarcodes).

## cURL Example ##

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}} {{< tab tabNum="1" >}}

```javascript
curl -v "https://api.groupdocs.cloud/v1/signature/barcodes" \
-X GET \
-H "Content-Type: application/json" \
-H "authorization: Bearer _0zqJ6w3enMdpEw5C6ZKm3lgYvHell1lHdx3vztekvBpCbZGqMvMplrKNrsVXih9Xe6738GSej2hb0BnwKVVz-ANEOnW0bGqjeiJcEySo2Y9-9VZ1K_rs_p4zZcsMoGNuDkL9G4rowGX9Wd1frChwRXzsJCpJUs9G5fGK-0kochaFTVdMgoOHU8JjUOQ5wiu-_ZQSbR0bMKRamxEyc_P_gv9NU7LTJQTCrP1SIJwem1WTX7GaTr8JRUYE0zsXH2vHUkJ1rNh-1RPblqE6wwrfxkklTCGxAWTxvoaSG-Ax-h2Zl9nZkBCAjS48zzz2kqIWS-K5WUmGPP9hAWQL00_deMB0Qi7xqvf2MWoJ831mFnyse-ZQ80fAqPyFBdYpS-xVFC0Uuc8rVHehydCxD0_oIJWkCU_GuDJpNMv6q4IpM-1RzFn"

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

{{< tabs tabTotal="4" tabID="10" tabName1="C#" tabName2="Java" tabName3="Python" tabName4="Ruby" >}} {{< tab tabNum="1" >}}

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Supported_Barcodes.cs >}}

{{< /tab >}} {{< tab tabNum="2" >}}

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Supported_Barcodes.java >}}

{{< /tab >}} {{< tab tabNum="3" >}}

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Supported_Barcodes.py >}}

{{< /tab >}} {{< tab tabNum="4" >}}

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Supported_Barcodes.rb >}}

{{< /tab >}} {{< /tabs >}}
