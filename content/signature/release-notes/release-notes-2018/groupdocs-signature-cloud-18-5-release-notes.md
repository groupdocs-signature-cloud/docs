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
* Search for Digital Signatures in PDF, SpreadSheet Document Formats and Word Processing Document Formats
* Search for Barcode Signatures in PDF, Images, SpreadSheet Document Formats, Word Processing Document Formats and Presentation Document Formats
* Search for QR-Code Signatures in PDF, Images, SpreadSheet Document Formats, Word Processing Document Formats and Presentation Document Formats
* Involved PageSetup extension to adjust pages selection for Signing, Verification and Search operations
* Added ability to Sign documents with list of Signature Options data
* Implemented ability to Verify documents with list of Verification Options data
* Introduced support to Search documents with list of Search Options data

## Full List of Issues Covering all Changes in this Release ##

|Key|Summary|Category
|---|---|---
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

### Sign documents with Stamp Signature #

To put Stamp Signature for supported Document formats (PDF, Images, SpreadSheet Document Formats, Word Processing Document Formats and Presentation Document Formats) Signature API provides new stamp options. For example to put Stamp Signature to Image **[ImagesSignStampOptionsData]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}})** is used that specify text, signature area, alignment, appearance, colors and another render features.

**Example**

**cURL**

### Retrieve access token. Use it for request.

```html
curl --request POST \
--url http:~/~/api.groupdocs.cloud/oauth2/token \
--header 'content-type: application/x-www-form-urlencoded' \
--data 'grant_type#client_credentials&client_id#[Your ClientId]&client_secret#[Your ClientSecret]'
```

### Put Stamp Signature on Images Document

```html
curl --request POST \
--url http:~/~/api.groupdocs.cloud/v1/signature/01_pages.png/stamp?folder#storage \
--header 'authorization: [Access Token]' \
--header 'content-type: application/json' \
--data '{ "outerLines": [ { "height": 20, "backgroundColor": { "Web": "BlueViolet" }, "text": " * John Smith * ", "font": { "fontFamily": "Arial", "fontSize": 12.0, "bold": true, "italic": true, "underline": false }, "textColor": { "Web": "DarkOrange" }, "textBottomIntent": 5, "textRepeatType": "FullTextRepeat", "outerBorder": { "style": "Default", "transparency": 0.7, "weight": 2.0, "color": {  "Web": "DarkOrange" } }, "innerBorder": { "style": "Default", "transparency": 0.5, "weight": 2.0, "color": {  "Web": "DarkOrange" } }, "visible": true } ], "innerLines": [ { "height": 30, "backgroundColor": { "Web": "Transparent", "Alpha": 0 }, "text": "John Smith", "font": { "fontFamily": "Times New Roman", "fontSize": 20.0, "bold": true, "italic": true, "underline": false }, "textColor": { "Web": "Gold" }, "textBottomIntent": 3, "textRepeatType": "None", "visible": true } ], "backgroundColor": { "Web": "CornflowerBlue" }, "backgroundColorCropType": "OuterArea", "backgroundImageCropType": "MiddleArea", "left": 2, "top": 2, "width": 200, "height": 150, "locationMeasureType": "Pixels", "sizeMeasureType": "Pixels", "rotationAngle": 0, "horizontalAlignment": "Left", "verticalAlignment": "Top", "margin": { "all": 10, "left": 10, "top": 10, "right": 10, "bottom": 10 }, "marginMeasureType": "Pixels", "opacity": 1.0, "signAllPages": false, "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [ 1 ] }, "OptionsType": "ImagesSignStampOptionsData" }'
```

The result Document created by Signature contains Image Signature File (see screenshot).

![](signature/images/ImagesWithStampSignature_small.png)

### Signature Collection ###

To put list of signatures on document (Cells, Images, PDF, Slides or Words) Signature provides new object **[SignOptionsCollectionData]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}})** that can contain one or more signature options. Please, use signature options which appropriate for current document format.

**Example**

**cURL for getting security token and start request**

### Retrieve access token. Use it for request.

```html
curl --request POST \
--url http:~/~/api.groupdocs.cloud/oauth2/token \
--header 'content-type: application/x-www-form-urlencoded' \
--data 'grant_type#client_credentials&client_id#[Your ClientId]&client_secret#[Your ClientSecret]'
```

### Put Text Signature to PDF Document

```html
curl --request POST \
--url http://api.groupdocs.cloud/v1/signature/01_pages.pdf/collection?folder=storage \
--header 'authorization: [Access Token]' \
--header 'content-type: application/json' \
--data '{ "items": [ { "barcodeTypeName": "Code39Standard", "borderVisiblity": true, "borderDashStyle": "Dash", "borderWeight": 12.0, "opacity": 0.8, "text": "123456789012", "left": 2, "top": 100, "width": 200, "height": 100, "locationMeasureType": "Pixels", "sizeMeasureType": "Pixels", "stretch": "None", "rotationAngle": 0, "horizontalAlignment": "Default", "verticalAlignment": "Default", "margin": { "all": 5, "left": 5, "top": 5, "right": 5, "bottom": 5 }, "marginMeasureType": "Pixels", "signAllPages": false, "font": { "fontFamily": "Times New Roman", "fontSize": 14.0, "bold": false, "italic": false, "underline": false }, "foreColor": { "Web": "DarkOrange" }, "borderColor": { "Web": "DarkOrange" }, "backgroundColor": { "Web": "BlueViolet" }, "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [  1 ] }, "OptionsType": "PdfSignBarcodeOptionsData" }, { "reason": "PdfDigitalReason", "contact": "PdfDigitalContact", "location": "PdfDigitalLocation", "visible": true, "password": "1234567890", "certificateGuid": "certificates\SherlockHolmes.pfx", "imageGuid": "images\signature_01.jpg", "left": 2, "top": 500, "width": 200, "height": 100, "locationMeasureType": "Pixels", "sizeMeasureType": "Pixels", "rotationAngle": 45, "horizontalAlignment": "Default", "verticalAlignment": "Default", "margin": { "all": 5, "left": 5, "top": 5, "right": 5, "bottom": 5 }, "marginMeasureType": "Pixels", "opacity": 0.9, "signAllPages": false, "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [  1 ] }, "OptionsType": "PdfSignDigitalOptionsData" } ] }'
```

The result contains data about signed file and status.

**JSON Result**

```html
{

  "fileName": "PdfWithoutAnySignature.pdf",
  "folder": "Output",
  "code": 200,
  "status": "OK"
}
```
