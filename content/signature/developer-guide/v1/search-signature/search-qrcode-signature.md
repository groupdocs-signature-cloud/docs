---
id: "search-qrcode-signature"
url: "signature/search-qrcode-signature"
title: "Search QRCode Signature"
productName: "GroupDocs.Signature Cloud"
weight: 3
description: ""
keywords: ""
---

{{< alert style="info" >}}
Note:  The features listed on this page are supported only in GroupDocs.Signature Cloud V1
{{< /alert >}}

# Introduction #

GroupDocs.Signature Cloud REST API supports to search QRCode signatures in supported document formats. It provides method to search Digital Signature in Document Pages with different options qrCodeTypeName, text, matchType and other search features by using [Search Options Object]({{< ref "signature/developer-guide/v1/common-resources/search-options-objects.md" >}}) data in request body.

# Search QRCode Signature #

You can search QRCode Signature on Document provided by fileName and document folder (if required) using following API. It expects [Search Options Object]({{< ref "signature/developer-guide/v1/common-resources/search-options-objects.md" >}}) data in request body.

It returns an object which contains document name, folder location and search result.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to search QRCode signature in a document](https://apireference.groupdocs.cloud/signature/#!/Search/PostSearchQRCode).

## cURL Example ##

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}} {{< tab tabNum="1" >}}

```javascript
curl --request POST \
--url http://api.groupdocs.cloud/v1/signature/SignedForVerificationAll.xlsx/QRCode/search?folder#signed \
--header 'authorization: [Access Token]' \
--header 'content-type: application/json' \
--data '{ "qrCodeTypeName": "Aztec", "text": "John Smith", "matchType": "Contains", "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [ 1 ] }, "searchAllPages": true, "OptionsType": "CellsSearchQRCodeOptionsData" }'

```

{{< /tab >}} {{< tab tabNum="2" >}}

```javascript
{
  "signatures": [
    {
      "qrCodeTypeName": "Aztec",
      "text": "John Smith",
      "signatureType": "CellsQRCodeSignatureData"
    },
    {
      "qrCodeTypeName": "Aztec",
      "text": "John Smith",
      "signatureType": "CellsQRCodeSignatureData"
    }
  ],
  "fileName": "SignedForVerificationAll.xlsx",
  "folder": "cells",
  "code": 200,
  "status": "OK"
}
{{< /tab >}} {{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](signature/available-sdks).

### Search QRCode Signature in a Document ###

{{< tabs tabTotal="5" tabID="10" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Python" tabName5="Ruby" >}} {{< tab tabNum="1" >}}

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Search_Signature_QRCode.cs >}}

{{< /tab >}} {{< tab tabNum="3" >}}

{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_QRCode_Search.php >}}

{{< /tab >}} {{< tab tabNum="2" >}}

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Search_Signature_QRCode.java >}}

{{< /tab >}} {{< tab tabNum="4" >}}

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Search_Signature_QRCode.py >}}

{{< /tab >}} {{< tab tabNum="5" >}}

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Search_Signature_QRCode.rb >}}

{{< /tab >}} {{< /tabs >}}

# Search QRCode Signature in a Document at Provided URL #

You can search QR-Code Signature for document at provided URL with [Search Options]({{< ref "signature/developer-guide/v1/common-resources/search-options-objects.md" >}}) using following API. It retrieves file from specified URL and tries to detect file type when fileName parameter is not specified.

It expects [Search Options]({{< ref "signature/developer-guide/v1/common-resources/search-options-objects.md" >}}) object data in request body. Based on passed Search Options settings proceeds with Document search, it returns object which contains result of searching process. The field Signatures keeps list of objects which represents found signatures like WordsQRCodeSignatureData.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to search QRCode signature in a document at provided URL](https://apireference.groupdocs.cloud/signature/#!/Search/PostSearchQRCodeFromUrl).

## cURL Example ##

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}} {{< tab tabNum="1" >}}

```javascript
curl --request POST \
--url http://api.groupdocs.cloud/v1/signature/qrcode/search?url#https%3a%2f%2fwww.dropbox.com%2fs%2fumokluz338w4ng7%2fone-page.docx%3fdl%3d1 \
--header 'authorization: [Access Token]' \
--header 'content-type: application/json' \
--data '{  "QRCodeTypeName" : "Aztec",  "MatchType" : "Contains",  "DocumentPageNumber": 1,  "Text": "John Smith",  "SearchAllPages" : true,  "OptionsType" : "WordsSearchQRCodeOptionsData" }'

```

{{< /tab >}} {{< tab tabNum="2" >}}

```javascript
{
  "fileName": "document.docx",
  "folder": "Output",
  "Code": "OK",
  "Status" : "OK",
  "Signatures" : [
    { QRCodeTypeName: "Aztec", Text: "John Smith" },
    { QRCodeTypeName: "Aztec", Text: "John Smith esq." }
    ]
}
{{< /tab >}} {{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](signature/available-sdks).

### Search QRCode Signature in a Document at Provided URL ###

{{< tabs tabTotal="5" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Python" tabName5="Ruby" >}} {{< tab tabNum="1" >}}

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Search_Signature_QRCode_URL.cs >}}

{{< /tab >}} {{< tab tabNum="3" >}}

{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_QRCode_Search_URL.php >}}

{{< /tab >}} {{< tab tabNum="2" >}}

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Search_Signature_QRCode_URL.java >}}

{{< /tab >}} {{< tab tabNum="4" >}}

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Search_Signature_QRCode_URL.py >}}

{{< /tab >}} {{< tab tabNum="5" >}}

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Search_Signature_QRCode_URL.rb >}}

{{< /tab >}} {{< /tabs >}}

