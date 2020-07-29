---
id: "working-with-signature-search"
url: "signature/working-with-signature-search"
title: "Working with Signature Search"
productName: "GroupDocs.Signature Cloud"
weight: 3
description: ""
keywords: ""
---






# Search Barcode Signature #

GroupDocs.Signature Cloud REST API supports to search Barcode signatures in supported document formats. It provides method to search Barcode Signature in Document Pages with different options barcodeType, Name, text, matchType and other search features by using [Search Options Object]({{< ref "signature/developer-guide/data-structures/searchsettings.md" >}})) data in request body.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to search Barcode signature in a document](https://apireference.groupdocs.cloud/signature/#/Sign/SearchSignatures).

## cURL Example ##





 Request

```html 
curl -X POST "https://api.groupdocs.cloud/v2.0/signature/search" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]" -H  "Content-Type: application/json" -d "{  \"FileInfo\": {    \"FilePath\": \"signaturedocs/one-page.pdf\",    \"StorageName\": \"MyStorage\",    \"VersionId\": \"\",    \"Password\": \"\"  },     \"SearchOptions\":    [    {        \"DocumentType\": \"Pdf\",        \"SignatureType\": \"Barcode\",          \"Page\": 1,        \"Text\": \"123\",        \"BarcodeType\": \"Code128\",        \"MatchType\": \"Contains\"    }   ] }"
 ```




 Response

```html 
{
  "FileInfo": {
    "FilePath": "one-page.pdf"
  },
  "Size" : 12345,
  "Signatures": 
  [
    {
       "DocumentType": "Pdf",
       "SignatureType": "Barcode",  
       "BarcodeType": "Code128",
       "Text": "1223344545454"
    }
   ]
}


 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Search Barcode Signature in a Document ###





 C#




{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Search_Barcode_Signature.cs >}}







 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Search_Barcode_Signature.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Search_Barcode_Signature.php >}}







 Ruby




{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Search_Barcode_Signature.rb >}}







 Node




{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Search_Barcode_Signature.js >}}







 Python




{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Search_Barcode_Signature.py >}}









# Search Digital Signature #

GroupDocs.Signature Cloud REST API supports to search Digital signatures in supported document formats. It provides method to search Digital Signature in Document Pages with different options by using [Search Options Object]({{< ref "signature/developer-guide/data-structures/searchsettings.md" >}})) data in request body.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to search Digital signature in a document](https://apireference.groupdocs.cloud/signature/#/Sign/SearchSignatures).

## cURL Example ##





 Request

```html 
curl -X POST "https://api.groupdocs.cloud/v2.0/signature/search" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]" -H  "Content-Type: application/json" -d "{  \"FileInfo\": {    \"FilePath\": \"signaturedocs/one-page.pdf\",    \"StorageName\": \"MyStorage\",    \"VersionId\": \"\",    \"Password\": \"\"  },     \"SearchOptions\":    [    {        \"DocumentType\": \"Pdf\",        \"SignatureType\": \"digital\",          \"Page\": 1,        \"Text\": \"123\",        \"MatchType\": \"Contains\"    }   ] }"
 ```




 Response

```html 
{
  "signatures": [
    {
      "comments": "Test comment",
      "isValid": false,
      "digitalSignatureType": 0,
      "signTime": "2017-01-25T10:41:54Z",
      "signatureType": "PdfDigitalSignatureData"
    }
  ],
  "fileName": "one-page.pdf",
  "folder": "signaturedocs",
  "code": 200,
  "status": "OK"
}
 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Search Digital Signature in a Document ###





 C#




{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Search_Digital_Signature.cs >}}







 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Search_Digital_Signature.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Search_Barcode_Signature.php >}}







 Ruby




{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Search_Barcode_Signature.rb >}}







 Node




{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Search_Digital_Signature.js >}}







 Python




{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Search_Digital_Signature.py >}}









# Search QRCode Signature #

GroupDocs.Signature Cloud REST API supports to search QRCode signatures in supported document formats. It provides method to search Digital Signature in Document Pages with different options qrCodeTypeName, text, matchType and other search features by using [Search Options Object]({{< ref "signature/developer-guide/data-structures/searchsettings.md" >}})) data in request body.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to search QRCode signature in a document](https://apireference.groupdocs.cloud/signature/#/Sign/SearchSignatures).

## cURL Example ##





 Request

```html 
curl -X POST "https://api.groupdocs.cloud/v2.0/signature/search" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]" -H  "Content-Type: application/json" -d "{  \"FileInfo\": {    \"FilePath\": \"Cells/SignedForVerificationAll.xlsx\",    \"StorageName\": \"MyStorage\",    \"VersionId\": \"\",    \"Password\": \"\"  },     \"SearchOptions\":    [    {        \"DocumentType\": \"xlsx\",        \"SignatureType\": \"digital\",          \"Page\": 1,        \"Text\": \"123\",        \"MatchType\": \"Contains\"    }   ] }"


 ```




 Response

```html 
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
 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Search QRCode Signature in a Document ###





 C#




{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Search_Search_QRCode_Signature.cs >}}







 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Search_Search_QRCode_Signature.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Search_QRCode_Signature.php >}}







 Ruby




{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Search_QRCode_Signature.rb >}}







 Node




{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Search_QRCode_Signature.js >}}







 Python




{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Search_QRCode_Signature.py >}}









# Search Multiple Signatures on Document #

GroupDocs.Signature Cloud REST API supports to search multiple signatures in a document. For example, you can search whether a document contains Text and Barcode Signatures at same time. To search list of signatures on document (Cells, Images, PDF, Slides or Words) Signature API provides an object **[SearchOptionsCollectionData]({{< ref "signature/developer-guide/data-structures/searchsettings.md" >}}))** that can contain one or more search options. Please, use search options which appropriate for current document format.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to search multiple signatures in a document](https://apireference.groupdocs.cloud/signature/#/Sign/SearchSignatures).

## cURL Example ##





 Request

```html 
curl -X POST "https://api.groupdocs.cloud/v2.0/signature/search" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]" -H  "Content-Type: application/json" -d "{  \"FileInfo\": {    \"FilePath\": \"pdf/SignedForVerificationAll.pdf\"StorageName\": \"MyStorage\",    \"VersionId\": \"\",    \"Password\": \"\"  },     \"SearchOptions\":    [    {        \"DocumentType\": \"xlsx\",        \"SignatureType\": \"digital\",          \"Page\": 1,        \"Text\": \"123\",        \"MatchType\": \"Contains\"    }   ] }"


 ```




 Response

```html 
{
  "signatures": [
    {
      "barcodeTypeName": "Code39Standard",
      "text": "123456789012",
      "signatureType": "PdfBarcodeSignatureData"
    },
    {
      "comments": "",
      "isValid": false,
      "digitalSignatureType": 0,
      "signTime": "2018-03-13T21:37:04",
      "signatureType": "PdfDigitalSignatureData"
    }
  ],
  "fileName": "SignedForVerificationAll.pdf",
  "folder": "pdf",
  "code": 200,
  "status": "OK"
}
 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Search Multiple Signatures ###





 C#




{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Search_Collection_Signature.cs >}}







 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Search_Collection_Signature.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Search_Collection_Signature.php >}}







 Ruby




{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Search_Collection_Signature.rb >}}







 Node




{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Search_Collection_Signature.js >}}







 Python




{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Search_Collection_Signature.py >}}







