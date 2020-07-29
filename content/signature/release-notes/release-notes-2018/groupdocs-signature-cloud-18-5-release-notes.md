---
id: "groupdocs-signature-cloud-18-5-release-notes"
url: "signature/groupdocs-signature-cloud-18-5-release-notes"
title: "GroupDocs.Signature Cloud 18.5 Release Notes"
productName: "GroupDocs.Signature Cloud"
weight: 2
description: ""
keywords: ""
---

## Major Features ##

There are 10 features and fixes in this release. The most notable are:

* Introduction of PHP SDK for GroupDocs.Signature Cloud 
* Introduced support of Image Document format (JPEG, PNG, BMP, GIF, multi frames TIFF)
* Implemented Stamp Signature type for supported Document formats PDF, Images, SpreadSheet Document Formats, Word Processing Document Formats and Presentation Document Formats
* Added Search operations for all supported Document formats with following features
** search for Digital Signatures in PDF, SpreadSheet Document Formats and Word Processing Document Formats
** search for Barcode Signatures in PDF, Images, SpreadSheet Document Formats, Word Processing Document Formats and Presentation Document Formats
** search for QR-Code Signatures in PDF, Images, SpreadSheet Document Formats, Word Processing Document Formats and Presentation Document Formats
* Involved PageSetup extension to adjust pages selection for Signing, Verification and Search operations
* Added ability to Sign documents with list of Signature Options data
* Implemented ability to Verify documents with list of Verification Options data
* Introduced support to Search documents with list of Search Options data

## Full List of Issues Covering all Changes in this Release ##

|Key
|---
|Summary
|Category
|SIGNATURECLOUD-202|Implement Verification for Images documents|New Feature
|SIGNATURECLOUD-195|Implement Signing for Images documents|New Feature
|SIGNATURECLOUD-193|Implement Pages Setup for SignOptionsData|New Feature
|SIGNATURECLOUD-170|Implement Search of QR-Code Signature methods|New Feature
|SIGNATURECLOUD-160|Implement Verification methods to support collection of options|New Feature
|SIGNATURECLOUD-154|Implement Signature method to support collection of options|New Feature
|SIGNATURECLOUD-153|Implement Search Options Collection Data support|New Feature
|SIGNATURECLOUD-148|Implement Search of Barcode Signature methods|New Feature
|SIGNATURECLOUD-142|Implement Search of Digital Signature methods|New Feature
|SIGNATURECLOUD-132|[Add PHP SDK for GroupDocs.Signature Cloud](https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-php)|New Feature
|SIGNATURECLOUD-177|Implement list of supported Barcode names|Improvement
|SIGNATURECLOUD-134|Improve Swagger specification of GroupDocs.Signature for Cloud|Improvement


## Public API and Backward Incompatible Changes ##


### [Sign documents with Stamp Signature]({{< ref "signature/developer-guide/signing-documents/working-with-stamp-signature.md" >}}) ###
|---|---

To put Stamp Signature for supported Document formats (PDF, Images, SpreadSheet Document Formats, Word Processing Document Formats and Presentation Document Formats) Signature API provides new stamp options. For example to put Stamp Signature to Image **[ImagesSignStampOptionsData]({{< ref "signature/developer-guide/common-resources/signature-options-objects.md" >}})** is used that specify text, signature area, alignment, appearance, colors and another render features.

 

**Example**

**cURL**



 

|
|---

~#~## Retrieve access token. Use it for request.




curl ~-~-request POST \




~-~-url http:~/~/api.groupdocs.cloud/oauth2/token \




~-~-header 'content-type: application/x-www-form-urlencoded' \




~-~-data 'grant_type#client_credentials&client_id#[Your AppSid]&client_secret#[Your AppKey]'




 




 




~#~## Put Stamp Signature on Images Document




curl ~-~-request POST \




~-~-url http:~/~/api.groupdocs.cloud/v1/signature/01_pages.png/stamp?folder#storage \




~-~-header 'authorization: [Access Token]' \




~-~-header 'content-type: application/json' \




~-~-data '{ "outerLines": [ { "height": 20, "backgroundColor": { "Web": "BlueViolet" }, "text": " * John Smith * ", "font": { "fontFamily": "Arial", "fontSize": 12.0, "bold": true, "italic": true, "underline": false }, "textColor": { "Web": "DarkOrange" }, "textBottomIntent": 5, "textRepeatType": "FullTextRepeat", "outerBorder": { "style": "Default", "transparency": 0.7, "weight": 2.0, "color": {  "Web": "DarkOrange" } }, "innerBorder": { "style": "Default", "transparency": 0.5, "weight": 2.0, "color": {  "Web": "DarkOrange" } }, "visible": true } ], "innerLines": [ { "height": 30, "backgroundColor": { "Web": "Transparent", "Alpha": 0 }, "text": "John Smith", "font": { "fontFamily": "Times New Roman", "fontSize": 20.0, "bold": true, "italic": true, "underline": false }, "textColor": { "Web": "Gold" }, "textBottomIntent": 3, "textRepeatType": "None", "visible": true } ], "backgroundColor": { "Web": "CornflowerBlue" }, "backgroundColorCropType": "OuterArea", "backgroundImageCropType": "MiddleArea", "left": 2, "top": 2, "width": 200, "height": 150, "locationMeasureType": "Pixels", "sizeMeasureType": "Pixels", "rotationAngle": 0, "horizontalAlignment": "Left", "verticalAlignment": "Top", "margin": { "all": 10, "left": 10, "top": 10, "right": 10, "bottom": 10 }, "marginMeasureType": "Pixels", "opacity": 1.0, "signAllPages": false, "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [ 1 ] }, "OptionsType": "ImagesSignStampOptionsData" }'




 


The result Document created by Signature contains Image Signature File (see screenshot).

![](signature/images/ImagesWithStampSignature_small.png)


### [Signature Collection]({{< ref "signature/developer-guide/signing-documents/working-with-signature-collection.md" >}}) ###
|---|---

To put list of signatures on document (Cells, Images, PDF, Slides or Words) Signature provides new object **[SignOptionsCollectionData]({{< ref "signature/developer-guide/common-resources/signature-options-objects.md" >}})** that can contain one or more signature options. Please, use signature options which appropriate for current document format.

 

**Example**


**cURL for getting security token and start request**



 

|
|---

~#~## Retrieve access token. Use it for request.




curl ~-~-request POST \




~-~-url http:~/~/api.groupdocs.cloud/oauth2/token \




~-~-header 'content-type: application/x-www-form-urlencoded' \




~-~-data 'grant_type#client_credentials&client_id#[Your AppSid]&client_secret#[Your AppKey]'




 




 




~#~## Put Text Signature to PDF Document




curl ~-~-request POST \




~-~-url http:~/~/api.groupdocs.cloud/v1/signature/01_pages.pdf/collection?folder#storage \




~-~-header 'authorization: [Access Token]' \




~-~-header 'content-type: application/json' \




~-~-data '{ "items": [ { "barcodeTypeName": "Code39Standard", "borderVisiblity": true, "borderDashStyle": "Dash", "borderWeight": 12.0, "opacity": 0.8, "text": "123456789012", "left": 2, "top": 100, "width": 200, "height": 100, "locationMeasureType": "Pixels", "sizeMeasureType": "Pixels", "stretch": "None", "rotationAngle": 0, "horizontalAlignment": "Default", "verticalAlignment": "Default", "margin": { "all": 5, "left": 5, "top": 5, "right": 5, "bottom": 5 }, "marginMeasureType": "Pixels", "signAllPages": false, "font": { "fontFamily": "Times New Roman", "fontSize": 14.0, "bold": false, "italic": false, "underline": false }, "foreColor": { "Web": "DarkOrange" }, "borderColor": { "Web": "DarkOrange" }, "backgroundColor": { "Web": "BlueViolet" }, "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [  1 ] }, "OptionsType": "PdfSignBarcodeOptionsData" }, { "reason": "PdfDigitalReason", "contact": "PdfDigitalContact", "location": "PdfDigitalLocation", "visible": true, "password": "1234567890", "certificateGuid": "certificates\SherlockHolmes.pfx", "imageGuid": "images\signature_01.jpg", "left": 2, "top": 500, "width": 200, "height": 100, "locationMeasureType": "Pixels", "sizeMeasureType": "Pixels", "rotationAngle": 45, "horizontalAlignment": "Default", "verticalAlignment": "Default", "margin": { "all": 5, "left": 5, "top": 5, "right": 5, "bottom": 5 }, "marginMeasureType": "Pixels", "opacity": 0.9, "signAllPages": false, "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [  1 ] }, "OptionsType": "PdfSignDigitalOptionsData" } ] }'




 


The result contains data about signed file and status.

**JSON Result**



 

|
|---

{




  "fileName": "PdfWithoutAnySignature.pdf",




  "folder": "Output",




  "code": 200,




  "status": "OK"




}




 


 


### [Verify Images documents with Barcode and QR-Code Signature]({{< ref "signature/developer-guide/signing-documents/working-with-qr-code-signature.md" >}}) ###
|---|---

This version(18.5) started support of Image docments verification with Barcode and QR-Code Signature. It introduced two new options for the purpose **[ImagesVerifyBarcodeOptionsData]({{< ref "signature/developer-guide/common-resources/verification-options-objects.md" >}}) **and** [ImagesVerifyQRCodeOptionsData]({{< ref "signature/developer-guide/common-resources/verification-options-objects.md" >}}).** For example to verify Barcode Signature in Image Document Signature API provides new options **[ImagesVerifyBarcodeOptionsData]({{< ref "signature/developer-guide/common-resources/verification-options-objects.md" >}})** that specify barcode text, barcode type and other features.

 

**Example**





 




**cURL**





 

|
|---

~#~## Retrieve access token. Use it for request.




curl ~-~-request POST \




~-~-url http:~/~/api.groupdocs.cloud/oauth2/token \




~-~-header 'content-type: application/x-www-form-urlencoded' \




~-~-data 'grant_type#client_credentials&client_id#[Your AppSid]&client_secret#[Your AppKey]'




 




 




~#~## Verify Barcode Signature in Image Document




curl ~-~-request POST \




~-~-url http:~/~/api.groupdocs.cloud/v1/signature/SignedForVerificationAll.png/barcode/verification?folder#storage \




~-~-header 'authorization: [Access Token]' \




~-~-header 'content-type: application/json' \




~-~-data '{ "barcodeTypeName": "Code39Standard", "matchType": "Contains", "text": "123456789012", "verifyAllPages": true, "isValid": false, "documentPageNumber": 1, "pagesSetup": { "firstPage": false, "lastPage": true, "oddPages": false, "evenPages": true, "pageNumbers": [ 1 ] }, "OptionsType": "ImagesVerifyBarcodeOptionsData" }'




 


JSON result contains verification status. If verification is successful result field is true.

**JSON Result**



 

|
|---

{




  "result": true,




  "fileName": "SignedForVerificationAll.png",




  "folder": "docimages",




  "code": 200,




  "status": "OK"




}




 



### [Verify Collection]({{< ref "signature/developer-guide/verifying-signature/working-with-verify-collection.md" >}}) ###
|---|---

To verify list of signatures in document (Cells, Images, PDF, Slides or Words) Signature provides new object **[VerifyOptionsCollectionData]({{< ref "signature/developer-guide/common-resources/verification-options-objects.md" >}})** that can contain one or more search options. Please, use search options which appropriate for current document format.

 

**Example**





 

**cURL**





 

|
|---

~#~## Retrieve access token. Use it for request.




curl ~-~-request POST \




~-~-url http:~/~/api.groupdocs.cloud/oauth2/token \




~-~-header 'content-type: application/x-www-form-urlencoded' \




~-~-data 'grant_type#client_credentials&client_id#[Your AppSid]&client_secret#[Your AppKey]'




 




 




~#~## Verify Signatures in PDF Document




curl ~-~-request POST \




~-~-url http:~/~/api.groupdocs.cloud/v1/signature/SignedForVerificationAll.pdf/collection/verification?folder#storage \




~-~-header 'authorization: [Access Token]' \




~-~-header 'content-type: application/json' \




~-~-data '{ "items": [ { "barcodeTypeName": "Code39Standard", "matchType": "Contains", "text": "123456789012", "verifyAllPages": true, "isValid": false, "documentPageNumber": 1, "pagesSetup": { "firstPage": false, "lastPage": true, "oddPages": false, "evenPages": true, "pageNumbers": [  1 ] }, "OptionsType": "PdfVerifyBarcodeOptionsData" }, { "password": "1234567890", "certificateGuid": "certificates\SherlockHolmes.pfx", "isValid": false, "documentPageNumber": 1, "pagesSetup": { "firstPage": false, "lastPage": true, "oddPages": false, "evenPages": true, "pageNumbers": [  1 ] }, "OptionsType": "PdfVerifyDigitalOptionsData" } ], "isValid": false }'




 


JSON result contains verification status. If verification is successful result field is true.

**JSON Result**



 

|
|---

{




  "result": true,




  "fileName": "SignedForVerificationAll.pdf",




  "folder": "pdf",




  "code": 200,




  "status": "OK"




}




 


 


### [Search Signatures in Documents](http://lisbon.dynabic.com/wiki/display/signature/v18.05+Search+Cells+documents+for+Barcode+Signatures) ###
|---|---

The support of this feature started from version 18.5. [search-options-objects]({{< ref "signature/developer-guide/common-resources/search-options-objects.md" >}}) are introduced in Signature API for the purpose.

* search for Digital Signatures in PDF, SpreadSheet Document Formats and Word Processing Document Formats
* search for Barcode Signatures in PDF, Images, SpreadSheet Document Formats, Word Processing Document Formats and Presentation Document Formats
* search for QR-Code Signatures in PDF, Images, SpreadSheet Document Formats, Word Processing Document Formats and Presentation Document Formats

For example To search Barcode Signatures in Cells Document (.xlsx, .xls, .xlsm, xlsb, csv, ods, ots, xltx, xltm file formats) Signature provides new options **[CellsSearchBarcodeOptionsData]({{< ref "signature/developer-guide/common-resources/search-options-objects.md" >}})** that specify barcodeTypeName, text, matchType and other search features.

 

**Example**





 

**cURL**





 

|
|---

~#~## Retrieve access token. Use it for request.




curl ~-~-request POST \




~-~-url http:~/~/api.groupdocs.cloud/oauth2/token \




~-~-header 'content-type: application/x-www-form-urlencoded' \




~-~-data 'grant_type#client_credentials&client_id#[Your AppSid]&client_secret#[Your AppKey]'




 




 




~#~## Search Barcode Signatures in Cells Document




curl ~-~-request POST \




~-~-url http:~/~/api.groupdocs.cloud/v1/signature/SignedForVerificationAll.xlsx/barcode/search?folder#storage \




~-~-header 'authorization: [Access Token]' \




~-~-header 'content-type: application/json' \




~-~-data '{ "barcodeTypeName": "Code39Standard", "text": "123456789012", "matchType": "Contains", "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [ 1 ] }, "searchAllPages": true, "OptionsType": "CellsSearchBarcodeOptionsData" }'




 


JSON result contains list of objects which represent signatures found in a document.

**JSON Result**



 

|
|---

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





### [Search Collection]({{< ref "signature/developer-guide/search-signature/working-with-search-collection.md" >}}) ###
|---|---

To search list of signatures in document (Cells, Images, PDF, Slides or Words) Signature provides new object **[SearchOptionsCollectionData]({{< ref "signature/developer-guide/common-resources/search-options-objects.md" >}})** that can contain one or more search options. Please, use search options which appropriate for current document format.

 

**Example**



**cURL**




 

|
|---

~#~## Retrieve access token. Use it for request.




curl ~-~-request POST \




~-~-url http:~/~/api.groupdocs.cloud/oauth2/token \




~-~-header 'content-type: application/x-www-form-urlencoded' \




~-~-data 'grant_type#client_credentials&client_id#[Your AppSid]&client_secret#[Your AppKey]'




 




 




~#~## Search Signatures in PDF Document




curl ~-~-request POST \




~-~-url http:~/~/api.groupdocs.cloud/v1/signature/SignedForVerificationAll.pdf/collection/search?folder#storage \




~-~-header 'authorization: [Access Token]' \




~-~-header 'content-type: application/json' \




~-~-data '{ "items": [ { "barcodeTypeName": "Code39Standard", "text": "123456789012", "matchType": "Contains", "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [  1 ] }, "searchAllPages": true, "OptionsType": "PdfSearchBarcodeOptionsData" }, { "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [  1 ] }, "searchAllPages": true, "OptionsType": "PdfSearchDigitalOptionsData" } ] }'




 


JSON result contains list of objects which represent signatures found in a document.

**JSON Result**



 

|
|---

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




 






 




















 
