---
id: "working-with-verify-collection"
url: "signature/working-with-verify-collection"
title: "Working with Verify Collection"
productName: "GroupDocs.Signature Cloud"
weight: 1
description: ""
keywords: ""
---

{{< alert style="info" >}}
Note:  The features listed on this page are supported only in GroupDocs.Signature Cloud V1
{{< /alert >}}










# Introduction #

GroupDocs.Signature Cloud REST API supports to verify multiple signatures in a document. For example, you can verify whether a document contains Text and Barcode Signatures at same time. To verify list of signatures on document (Cells, Images, PDF, Slides or Words) Signature API provides an object **[VerifyOptionsCollectionData]({{< ref "signature/developer-guide/common-resources/verification-options-objects.md" >}})** that can contain one or more verify options. Please, use verify options which appropriate for current document format.

# Verify Multiple Signatures to Document #

You can verify multiple Signatures on Document at same time provided by fileName and document folder (if required) using following API. It expects [VerifyOptionsCollectionData]({{< ref "signature/developer-guide/common-resources/verification-options-objects.md" >}}) object data in request body. You can add required verify options to this object as per your document format.

It returns an object which contains document name, folder location and signing result.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to verify document with multiple signatures](https://apireference.groupdocs.cloud/signature/#!/Verification/PostVerificationCollection).

## cURL Example ##





 Request

```html 
curl --request POST \
--url http://api.groupdocs.cloud/v1/signature/SignedForVerificationAll.pdf/collection/verification?folder#storage \
--header 'authorization: [Access Token]' \
--header 'content-type: application/json' \
--data '{ "items": [ { "barcodeTypeName": "Code39Standard", "matchType": "Contains", "text": "123456789012", "verifyAllPages": true, "isValid": false, "documentPageNumber": 1, "pagesSetup": { "firstPage": false, "lastPage": true, "oddPages": false, "evenPages": true, "pageNumbers": [  1 ] }, "OptionsType": "PdfVerifyBarcodeOptionsData" }, { "password": "1234567890", "certificateGuid": "certificates\SherlockHolmes.pfx", "isValid": false, "documentPageNumber": 1, "pagesSetup": { "firstPage": false, "lastPage": true, "oddPages": false, "evenPages": true, "pageNumbers": [  1 ] }, "OptionsType": "PdfVerifyDigitalOptionsData" } ], "isValid": false }'

 ```




 Response

```html 
{
  "result": true,
  "fileName": "SignedForVerificationAll.pdf",
  "folder": "pdf",
  "code": 200,
  "status": "OK"
}
 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Verify Multiple Signatures ###





 C#




{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Signature_Collection_Verify.cs >}}







 PHP




{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_Collection_Verify.php >}}







 Java




{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Signature_Collection_Verify.java >}}







 Python




{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Signature_Collection_Verify.py >}}







 Ruby




{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Signature_Signature_Collection_Verify.rb >}}







 

# Verify Multiple Signatures in a Document at Provided URL #

You can verify multiple Signatures on Document at same time  from specified URL and document folder (if required) using following API. It expects [VerifyOptionsCollectionData]({{< ref "signature/developer-guide/common-resources/verification-options-objects.md" >}}) object data in request body. You can add required verify options to this object as per your document format.

It returns an object which contains document name, folder location and signing result.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to verify document with multiple signatures at provided url](https://apireference.groupdocs.cloud/signature/#!/Verification/PostVerificationCollection).

## cURL Example ##





 Request

```html 
curl --request POST \
--url http://api.groupdocs.cloud/v1/signature/collection/verification?url#https%3a%2f%2fwww.dropbox.com%2fs%2fumokluz338w4ng7%2fone-page.docx%3fdl%3d1 \
--header 'authorization: [Access Token]' \
--header 'content-type: application/json' \
--data '{ "items": [ { "barcodeTypeName": "Code39Standard", "matchType": "Contains", "text": "123456789012", "verifyAllPages": true, "isValid": false, "documentPageNumber": 1, "pagesSetup": { "firstPage": false, "lastPage": true, "oddPages": false, "evenPages": true, "pageNumbers": [  1 ] }, "OptionsType": "PdfVerifyBarcodeOptionsData" }, { "password": "1234567890", "certificateGuid": "certificates\SherlockHolmes.pfx", "isValid": false, "documentPageNumber": 1, "pagesSetup": { "firstPage": false, "lastPage": true, "oddPages": false, "evenPages": true, "pageNumbers": [  1 ] }, "OptionsType": "PdfVerifyDigitalOptionsData" } ], "isValid": false }'

 ```




 Response

```html 
{
  "result": true,
  "fileName": "SignedForVerificationAll.pdf",
  "folder": "pdf",
  "code": 200,
  "status": "OK"
}
 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Add Multiple Signatures in a Document at Provided URL ###





 C#




{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Signature_Collection_Verify_FromUrl.cs >}}







 PHP




{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_Collection_Verify_URL.php >}}







 Java




{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Signature_Collection_Verify_FromUrl.java >}}







 Python




{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Signature_Collection_Verify_FromUrl.py >}}







 Ruby




{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Signature_Signature_Collection_Verify_FromUrl.rb >}}







