---
id: "groupdocs-signature-cloud-18-8-release-notes"
url: "signature/groupdocs-signature-cloud-18-8-release-notes"
title: "GroupDocs.Signature Cloud 18.8 Release Notes"
productName: "GroupDocs.Signature Cloud"
weight: 1
description: ""
keywords: ""
---

## Major Features ##

There about 20 features and fixes in this release. The most notable are:

* Introduced additional properties of Text Signature.
* Implemented different background Brush styles for Text and Stamp Signatures for all supported document types.
* Involved additional properties for QR-Code Signature
* Added ability to put Logo into QR-Code Signature
* Improved Exception handling and error codes.

## Full List of Issues Covering all Changes in this Release ##

|Key|Summary|Category
|---|---|---
|SIGNATURECLOUD-308|Update Search QR-Code Options|New Feature
|SIGNATURECLOUD-307|Update Search Barcode Options|New Feature
|SIGNATURECLOUD-305|Update Signature QR-Code Options with new properties|New Feature
|SIGNATURECLOUD-304|Update Signature Barcode Options|New Feature
|SIGNATURECLOUD-303|Update Signature Digital Options with new properties|New Feature
|SIGNATURECLOUD-302|Implement Verify Options Extensions with new properties|New Feature
|SIGNATURECLOUD-295|Update Signature Options Appearances with new properties|New Feature
|SIGNATURECLOUD-292|Update Verification QRCode Options with new properties|New Feature
|SIGNATURECLOUD-288|Update Verification Text Options with new properties|New Feature
|SIGNATURECLOUD-287|Update Signature Stamp Options with new properties|New Feature
|SIGNATURECLOUD-286|Update Signature Image Options with new properties|New Feature
|SIGNATURECLOUD-285|Update Signature Text Options with new properties|New Feature
|SIGNATURECLOUD-202|Implement Verification for Images documents|New Feature
|SIGNATURECLOUD-187|Implement Brush Styles features support|New Feature
|SIGNATURECLOUD-160|Implement Verification methods to support collection of options|New Feature
|SIGNATURECLOUD-284|Improve Exception handling, implement Signature Exceptions support|Improvement
|SIGNATURECLOUD-279|Add specific fields to PdfDigitalSignatureData|Improvement
|SIGNATURECLOUD-134|Improve Swagger specification of GroupDocs.Signature for Cloud|Improvement
|SIGNATURECLOUD-269|Fix Exception "Invalid provider type specified."|Bug

## Public API and Backward Incompatible Changes ##

### Apply Background Brush for Text Signatures ###

Signature Text Options and all inherited classes have been updated with newly added property **BackgroundBrush** which support following brush types:

**§ Linear Gradient Brush**

```javascript

"backgroundBrush": {"startColor": {"web": "CornflowerBlue"}, "endColor": {"web": "DarkBlue"}, "angle": 0.0, "brushType": "LinearGradientBrush"}

```

**§ Radial Gradient Brush**

```javascript

"backgroundBrush": { "innerColor": {"web": "CornflowerBlue"}, "outerColor": {"web": "DarkBlue"}, "brushType": "RadialGradientBrush"}

```

**§ Solid Brush**

```javascript

"backgroundBrush": {"color": {"web": "DarkBlue"}, "brushType": "SolidBrush"}

```

**§ Texture Brush**

```javascript
"backgroundBrush": {"imageGuid": "images\signature_01.jpg", "brushType": "TextureBrush"}
```

```javascript

### Retrieve access token. Use it for request.
curl --request POST \
--url http://api.groupdocs.cloud/oauth2/token \
--header 'content-type: application/x-www-form-urlencoded' \
--data 'grant_type#client_credentials&#x26;client_id#[Your AppSid]&#x26;client_secret#[Your AppKey]'

### Put Text Signature with brush to Slides Document
curl --request POST \
--url http://api.groupdocs.cloud/v1/signature/01_pages.pptx/text?folder#storage \
--header 'authorization: [Access Token]' \
--header 'content-type: application/json' \
--data '{ "borderTransparency": 0.0, "borderWeight": 1.0, "backgroundTransparency": 0.0, "signatureImplementation": "TextStamp", "backgroundBrush": { "startColor": { "web": "CornflowerBlue" }, "endColor": { "web": "DarkBlue" }, "angle": 0.0 , "brushType": "LinearGradientBrush"}, "left": 1, "top": 1, "width": 200, "height": 50, "locationMeasureType": "Pixels", "sizeMeasureType": "Pixels", "stretch": "None", "rotationAngle": 0, "horizontalAlignment": "Left", "verticalAlignment": "Top", "margin": { "all": 10, "left": 10, "top": 10, "right": 10, "bottom": 10 }, "marginMeasureType": "Pixels", "text": "John Smith", "signAllPages": false, "font": { "fontFamily": "Times New Roman", "fontSize": 24.0, "bold": true, "italic": false, "underline": false }, "foreColor": { "Web": "DarkSlateBlue" }, "borderColor": { "Web": "Black" }, "backgroundColor": { "Web": "Transparent", "Alpha": 0 }, "documentPageNumber": 0, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [ 1 ] }, "OptionsType": "SlidesSignTextOptionsData" }'

```

The result Document created by Signature contains Text Signature with Linear Gradient Brush (see screenshot).

![](signature/images/SlidesSignatureBrush.png)

### Barcode type name is no longer required for searching of Barcode Signatures ###

To search Barcode Signatures in PDF Document (.pdf file format) Signature provides options **PdfSearchBarcodeOptionsData** that specify BarcodeTypeName, text, matchType and other search features.

 BarcodeTypeName attribute is no longer required

```javascript

### Retrieve access token. Use it for request.
curl --request POST \
--url http://api.groupdocs.cloud/oauth2/token \
--header 'content-type: application/x-www-form-urlencoded' \
--data 'grant_type#client_credentials&#x26;client_id#[Your AppSid]&#x26;client_secret#[Your AppKey]'

### Search Barcode Signatures in Pdf Document
curl --request POST \
--url http://api.groupdocs.cloud/v1/signature/SignedForVerificationAll.pdf/barcode/search?folder#signed \
--header 'authorization: [Access Token]' \
--header 'content-type: application/json' \
--data '{ "text": "12345678", "matchType": "Contains", "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [ 1 ] }, "searchAllPages": false, "OptionsType": "PdfSearchBarcodeOptionsData" }'

```

JSON result contains list of objects which represent signatures found in a document.

```javascript
{
  "signatures": [
    {
      "barcodeTypeName": "Code39Standard",
      "text": "123456789012",
      "signatureType": "PdfBarcodeSignatureData"
    }
  ],
  "fileName": "SignedForVerificationAll.pdf",
  "folder": "pdf",
  "code": 200,
  "status": "OK"
}
```

### QR-Code type name is no longer required for searching of QR-Code Signatures ###

To search QR-Code Signatures in PDF Document (.pdf file format) Signature provides options **PdfSearchQRCodeOptionsData** that specify QRCodeTypeName, text, matchType and other search features.

 QRCodeTypeName attribute is no longer required

```javascript

### Retrieve access token. Use it for request.
curl --request POST \
--url http://api.groupdocs.cloud/oauth2/token \
--header 'content-type: application/x-www-form-urlencoded' \
--data 'grant_type#client_credentials&#x26;client_id#[Your AppSid]&#x26;client_secret#[Your AppKey]'

### Search QRCode Signatures in Pdf Document
curl --request POST \
--url http://api.groupdocs.cloud/v1/signature/SignedForVerificationAll.pdf/qrcode/search?folder#signed \
--header 'authorization: [Access Token]' \
--header 'content-type: application/json' \
--data '{ "text": "12345678", "matchType": "Contains", "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [ 1 ] }, "searchAllPages": false, "OptionsType": "PdfSearchQRCodeOptionsData" }'

```

JSON result contains list of objects which represent signatures found in a document.

```javascript
{
  "signatures": [
    {
      "qrcodeTypeName": "QR",
      "text": "123456789012",
      "signatureType": "PdfQRCodeSignatureData"
    }
  ],
  "fileName": "SignedForVerificationAll.pdf",
  "folder": "pdf",
  "code": 200,
  "status": "OK"
}
```

### Setup Background Brush for Stamp Signatures ###

Signature Stamp Options and all inherited classes have been updated with newly added property **BackgroundBrush** which support following brush types:

**§ Linear Gradient Brush**

```javascript

"backgroundBrush": {"startColor": {"web": "CornflowerBlue"}, "endColor": {"web": "DarkBlue"}, "angle": 0.0, "brushType": "LinearGradientBrush"}

```

**§ Radial Gradient Brush**

```javascript

"backgroundBrush": { "innerColor": {"web": "CornflowerBlue"}, "outerColor": {"web": "DarkBlue"}, "brushType": "RadialGradientBrush"}

```

**§ Solid Brush**

```javascript

"backgroundBrush": {"color": {"web": "DarkBlue"}, "brushType": "SolidBrush"}

```

**§ Texture Brush**

```javascript

"backgroundBrush": {"imageGuid": "images\signature_01.jpg", "brushType": "TextureBrush"}

```

List of updated options: **SignStampOptionsData, CellsSignStampOptionsData, ImagesSignStampOptionsData, PdfSignStampOptionsData, SlidesSignStampOptionsData, WordsSignStampOptionsData**.

```javascript

### Retrieve access token. Use it for request.
curl --request POST \
--url http://api.groupdocs.cloud/oauth2/token \
--header 'content-type: application/x-www-form-urlencoded' \
--data 'grant_type#client_credentials&#x26;client_id#[Your AppSid]&#x26;client_secret#[Your AppKey]'

### Put Stamp Signature with brush on Slides Document
curl --request POST \
--url http://api.groupdocs.cloud/v1/signature/01_pages.pptx/stamp?folder#storage \
--header 'authorization: [Access Token]' \
--header 'content-type: application/json' \
--data '{ "outerLines": [ { "height": 20, "backgroundColor": { "Web": "BlueViolet" }, "text": " * John Smith * ", "font": { "fontFamily": "Arial", "fontSize": 12.0, "bold": true, "italic": true, "underline": false }, "textColor": { "Web": "DarkOrange" }, "textBottomIntent": 5, "textRepeatType": "FullTextRepeat", "outerBorder": { "style": "Default", "transparency": 0.7, "weight": 2.0, "color": {  "Web": "DarkOrange" } }, "innerBorder": { "style": "Default", "transparency": 0.5, "weight": 2.0, "color": {  "Web": "DarkOrange" } }, "visible": true } ], "innerLines": [ { "height": 30, "backgroundColor": { "Web": "Transparent", "Alpha": 0 }, "text": "John Smith", "font": { "fontFamily": "Times New Roman", "fontSize": 20.0, "bold": true, "italic": true, "underline": false }, "textColor": { "Web": "Gold" }, "textBottomIntent": 3, "textRepeatType": "None", "visible": true } ], "backgroundColor": { "Web": "CornflowerBlue" }, "backgroundBrush": { "startColor": { "web": "LightBlue" }, "endColor": { "web": "DarkBlue" }, "angle": 45.0, "brushType": "LinearGradientBrush" }, "backgroundColorCropType": "OuterArea", "backgroundImageCropType": "MiddleArea", "left": 2, "top": 2, "width": 200, "height": 150, "locationMeasureType": "Pixels", "sizeMeasureType": "Pixels", "rotationAngle": 0, "horizontalAlignment": "Left", "verticalAlignment": "Top", "margin": { "all": 10, "left": 10, "top": 10, "right": 10, "bottom": 10 }, "marginMeasureType": "Pixels", "opacity": 1.0, "signAllPages": false, "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [ 1 ] }, "OptionsType": "SlidesSignStampOptionsData" }'

```

The result Document created by Signature contains Text Signature with Linear Gradient Brush (see screenshot).

![](signature/images/StampSignatureBrush.png)

### Setup QR-Code Logo image (Signature QR-Code Options) ###

Signature QR-Code Options have been updated with newly added property **LogoGuid** which support QR-Code background image located at the center of QR-Code

**Setup LogoGuid**

```javascript

"logoGuid": "images/logo1.png"

```

To put QRCode Signature to Image Document (png, jpeg, gif, tiff and another file formats) Signature provides new options **[ImagesSignQRCodeOptionsData]("ImagesSignQRCodeOptionsDataObject")** that specify text, signature area, alignment, appearance, colors and another render features.

```javascript

### Retrieve access token. Use it for request.
curl --request POST \
--url http://api.groupdocs.cloud/oauth2/token \
--header 'content-type: application/x-www-form-urlencoded' \
--data 'grant_type#client_credentials&#x26;client_id#[Your AppSid]&#x26;client_secret#[Your AppKey]'

### Put QRCode Signature on Images Document with logo
curl --request POST \
--url http://api.groupdocs.cloud/v1/signature/01_pages.png/qrcode?folder#storage \
--header 'authorization: [Access Token]' \
--header 'content-type: application/json' \
--data '{ "qrCodeTypeName": "Aztec", "borderVisiblity": true, "borderDashStyle": "Solid", "borderWeight": 1.0, "opacity": 0.8, "text": "123456789012", "left": 2, "top": 2, "width": 200, "height": 100, "locationMeasureType": "Pixels", "sizeMeasureType": "Pixels", "stretch": "None", "rotationAngle": 0, "horizontalAlignment": "Left",
"logoGuid": "images/logo1.png"
"verticalAlignment": "Top", "margin": { "all": 10, "left": 10, "top": 10, "right": 10, "bottom": 10 }, "marginMeasureType": "Pixels", "signAllPages": false, "font": { "fontFamily": "Times New Roman", "fontSize": 14.0, "bold": false, "italic": false, "underline": false }, "foreColor": { "Web": "Black" }, "borderColor": { "Web": "Black" }, "backgroundColor": { "Web": "Transparent", "Alpha": 0 }, "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [ 1 ] }, "OptionsType": "ImagesSignQRCodeOptionsData" }'

```

The result Document created by Signature contains Image Signature File (see screenshot).

![](signature/images/ImagesWithQRCodeSignature_small.png)

### Updated Signature Text Options with text alignments ###

**CellsSignTextOptionsData, ImagesSignTextOptionsData, PdfSignTextOptionsData, SlidesSignTextOptionsData, WordsSignTextOptionsData** classes were updated with newly added properties **TextHorizontalAlignment** and **TextVerticalAlignment** .

**§ TextHorizontalAlignment**

```javascript

"textHorizontalAlignment": "Left"

```

**§ TextVerticalAlignment**

```javascript

"textVerticalAlignment": "Top"

```

There is an example of signing document with text alignments.

```javascript
### Retrieve access token. Use it for request.
curl --request POST \
--url http://api.groupdocs.cloud/oauth2/token \
--header 'content-type: application/x-www-form-urlencoded' \
--data 'grant_type#client_credentials&#x26;client_id#[Your AppSid]&#x26;client_secret#[Your AppKey]'

### Put Text Signature on Image Document
curl --request POST \
--url http://api.groupdocs.cloud/v1/signature/01_pages.png/text?folder#storage \
--header 'authorization: [Access Token]' \
--header 'content-type: application/json' \
--data '{ "borderDashStyle": 0, "borderTransparency": 0.0, "borderWeight": 5.0, "backgroundTransparency": 0.0, "signatureImplementation": "TextAsImage", "opacity": 1.0, "documentPageNumber": 1, "pagesSetup": { "firstPage": false, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [] }, "signAllPages": false, "textHorizontalAlignment": "Left", "textVerticalAlignment": "Top", "left": 1, "top": 1, "width": 200, "height": 40, "locationMeasureType": "Pixels", "sizeMeasureType": "Pixels", "stretch": "None", "rotationAngle": 0, "horizontalAlignment": "Left", "verticalAlignment": "Top", "margin": { "all": 10, "left": 10, "top": 10, "right": 10, "bottom": 10 }, "marginMeasureType": "Pixels", "text": " John Smith", "font": { "fontFamily": "Times New Roman", "fontSize": 24.0, "bold": true, "italic": false, "underline": false }, "foreColor": { "Web": "DarkSlateBlue" }, "borderColor": { "Web": "DarkSlateBlue" }, "backgroundColor": { "Web": "Goldenrod" }, "OptionsType": "ImagesSignTextOptionsData" }'

```

