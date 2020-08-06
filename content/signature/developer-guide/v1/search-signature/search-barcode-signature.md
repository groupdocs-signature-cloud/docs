---
id: "search-barcode-signature"
url: "signature/search-barcode-signature"
title: "Search Barcode Signature"
productName: "GroupDocs.Signature Cloud"
weight: 1
description: ""
keywords: ""
---

{{< alert style="info" >}}
Note:  The features listed on this page are supported only in GroupDocs.Signature Cloud V1
{{< /alert >}}










# Introduction #

GroupDocs.Signature Cloud REST API supports to search Barcode signatures in supported document formats. It provides method to search Barcode Signature in Document Pages with different options barcodeType, Name, text, matchType and other search features by using [Search Options Object]({{< ref "signature/developer-guide/v1/common-resources/search-options-objects.md" >}}) data in request body.

# Search Barcode Signature #

You can search Barcode Signature on Document provided by fileName and document folder (if required) using following API. It expects [Search Options Object]({{< ref "signature/developer-guide/v1/common-resources/search-options-objects.md" >}}) data in request body.

It returns an object which contains document name, folder location and search result.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to search Barcode signature in a document](https://apireference.groupdocs.cloud/signature/#!/Search/PostSearchBarcode).

## cURL Example ##





 Request

```html 
curl --request POST \
--url http://api.groupdocs.cloud/v1/signature/SignedForVerificationAll.xlsx/barcode/search?folder#signed \
--header 'authorization: [Access Token]' \
--header 'content-type: application/json' \
--data '{ "barcodeTypeName": "Code39Standard", "text": "123456789012", "matchType": "Contains", "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [ 1 ] }, "searchAllPages": true, "OptionsType": "CellsSearchBarcodeOptionsData" }'

 ```




 Response

```html 
{
  "signatures": [
    {
      "barcodeTypeName": "Code39Standard",
      "text": "123456789012",
      "signatureType": "CellsBarcodeSignatureData"
    },
    {
      "barcodeTypeName": "Code39Standard",
      "text": "123456789012",
      "signatureType": "CellsBarcodeSignatureData"
    }
  ],
  "fileName": "SignedForVerificationAll.xlsx",
  "folder": "cells",
  "code": 200,
  "status": "OK"
}
 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Search Barcode Signature in a Document ###





 C#




{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Search_Signature_Barcode.cs >}}







 PHP




{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Barcode_Search.php >}}







 Java




{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Search_Signature_Barcode.java >}}







 Python




{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Search_Signature_Barcode.py >}}







 Ruby




{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Search_Signature_Barcode.rb >}}









# Search Barcode Signature in Document at Provided URL #

You can search Barcode Signature for a Document at provided URL using following API. 

It retrieves file from specified URL and tries to detect file type when fileName parameter is not specified. It expects [search-options-objects]({{< ref "signature/developer-guide/v1/common-resources/search-options-objects.md" >}}) object data in request body.

Based on passed Search Options settings proceeds with Document searching, it returns object which contains result of searching process.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to search Barcode signature in a document at provided URL](https://apireference.groupdocs.cloud/signature/#!/Search/PostSearchBarcodeFromUrl).

## cURL Example ##





 Request

```html 
curl --request POST \
--url http://api.groupdocs.cloud/v1/signature/barcode/search?url#https%3a%2f%2fwww.dropbox.com%2fs%2fumokluz338w4ng7%2fone-page.docx%3fdl%3d1 \
--header 'authorization: [Access Token]' \
--header 'content-type: application/json' \
--data '{ "BarcodeTypeName" : "Code128",  "MatchType" : "Contains",  "DocumentPageNumber": 1,  "Text": "John Smith",  "SearchAllPages" : true,  "OptionsType" : "WordsSearchBarcodeOptionsData" }'

 ```




 Response

```html 
{
  "fileName": "one-page.docx",
  "folder": "Output",
  "Code": "OK",
  "Status" : "OK",
  "Signatures" : [
    { BarcodeTypeName: "Code128", Text: "John Smith" }, 
    { BarcodeTypeName: "Code128", Text: "John Smith esq." }
    ]
}
 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Search Barcode Signature in a Document at Provided URL ###





 C#




{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Search_Signature_Barcode_URL.cs >}}







 PHP




{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Barcode_Search_URL.php >}}







 Java




{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Search_Signature_Barcode_URL.java >}}







 Python




{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Search_Signature_Barcode_URL.py >}}







 Ruby




{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Search_Signature_Barcode_URL.rb >}}






