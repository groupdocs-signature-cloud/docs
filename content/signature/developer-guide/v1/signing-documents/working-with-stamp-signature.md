---
id: "working-with-stamp-signature"
url: "signature/working-with-stamp-signature"
title: "Working with Stamp Signature"
productName: "GroupDocs.Signature Cloud"
weight: 6
description: ""
keywords: ""
---

{{< alert style="info" >}}
Note:  The features listed on this page are supported only in GroupDocs.Signature Cloud V1
{{< /alert >}}










# Introduction #

GroupDocs.Signature Cloud REST API supports to put Stamp Signature on supported file format. It provides methods to create Stamp Signature in Document Pages with different options to add image as stamp, location, alignment, font, margins and appearances by using [Signature Options Object]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}) data in request body.

# Add Stamp Signature to Document #

You can create Stamp Signature on Document provided by fileName and document folder (if required) using following API. It expects [Signature Options Object]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}) data in request body.

It returns an object which contains document name, folder location and command status.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add Stamp signature to a document](https://apireference.groupdocs.cloud/signature/#!/Signing/PostStamp).

## cURL Example ##





 Requestcurl ~-~-request POST \
~-~-url http:~/~/api.groupdocs.cloud/v1/signature/01_pages.png/stamp?folder#storage \
~-~-header 'authorization: [Access Token]' \
~-~-header 'content-type: application/json' \
~-~-data '{ "outerLines": [ { "height": 20, "backgroundColor": { "Web": "BlueViolet" }, "text": " * John Smith * ", "font": { "fontFamily": "Arial", "fontSize": 12.0, "bold": true, "italic": true, "underline": false }, "textColor": { "Web": "DarkOrange" }, "textBottomIntent": 5, "textRepeatType": "FullTextRepeat", "outerBorder": { "style": "Default", "transparency": 0.7, "weight": 2.0, "color": { "Web": "DarkOrange" } }, "innerBorder": { "style": "Default", "transparency": 0.5, "weight": 2.0, "color": { "Web": "DarkOrange" } }, "visible": true } ], "innerLines": [ { "height": 30, "backgroundColor": { "Web": "Transparent", "Alpha": 0 }, "text": "John Smith", "font": { "fontFamily": "Times New Roman", "fontSize": 20.0, "bold": true, "italic": true, "underline": false }, "textColor": { "Web": "Gold" }, "textBottomIntent": 3, "textRepeatType": "None", "visible": true } ], "backgroundColor": { "Web": "CornflowerBlue" }, "backgroundColorCropType": "OuterArea", "backgroundImageCropType": "MiddleArea", "left": 2, "top": 2, "width": 200, "height": 150, "locationMeasureType": "Pixels", "sizeMeasureType": "Pixels", "rotationAngle": 0, "horizontalAlignment": "Left", "verticalAlignment": "Top", "margin": { "all": 10, "left": 10, "top": 10, "right": 10, "bottom": 10 }, "marginMeasureType": "Pixels", "opacity": 1.0, "signAllPages": false, "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [ 1 ] }, "OptionsType": "ImagesSignStampOptionsData" }'






 Response

```html 
{
  "fileName": "01_pages.png",
  "folder": "Output",
  "code": 200,
  "status": "OK"
}
 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Add Stamp Signature to Document ###





 C#




{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Signature_Stamp.cs >}}







 PHP




{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_Stamp.php >}}







 Java




{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Signature_Stamp.java >}}







 Python




{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Signature_Stamp.py >}}







 Ruby




{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Signature_Signature_Stamp.rb >}}









# Add Stamp Signature to Document at Provided URL #

You can create Stamp Signature for document at provided URL with [signature-options-objects]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}). It retrieves file from specified URL and tries to detect file type when fileName parameter is not specified. It saves retrieved file in storage, by using fileName and folder parameters to specify desired file name and folder to save file. When file with specified name already exists in storage new unique file name will be used for file. It expects [Signature Options Object]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}) data in request body and returns object which contains document name and folder location.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add Stamp signature to a document at provided URL](https://apireference.groupdocs.cloud/signature/#!/Signing/PostStampFromUrl).

## cURL Example ##





 Request

```html 
curl --request POST \
--url http://api.groupdocs.cloud/v1/signature/stamp?url#https%3A%2F%2Fwww.dropbox.com%2Fs%2F3hbc18wympow0j1%2Ftest.png%3Fdl%3D1 \
--header 'authorization: [Access Token]' \
--header 'content-type: application/json' \
--data '{ "outerLines": [ { "height": 20, "backgroundColor": { "Web": "BlueViolet" }, "text": " * John Smith * ", "font": { "fontFamily": "Arial", "fontSize": 12.0, "bold": true, "italic": true, "underline": false }, "textColor": { "Web": "DarkOrange" }, "textBottomIntent": 5, "textRepeatType": "FullTextRepeat", "outerBorder": { "style": "Default", "transparency": 0.7, "weight": 2.0, "color": { "Web": "DarkOrange" } }, "innerBorder": { "style": "Default", "transparency": 0.5, "weight": 2.0, "color": { "Web": "DarkOrange" } }, "visible": true } ], "innerLines": [ { "height": 30, "backgroundColor": { "Web": "Transparent", "Alpha": 0 }, "text": "John Smith", "font": { "fontFamily": "Times New Roman", "fontSize": 20.0, "bold": true, "italic": true, "underline": false }, "textColor": { "Web": "Gold" }, "textBottomIntent": 3, "textRepeatType": "None", "visible": true } ], "backgroundColor": { "Web": "CornflowerBlue" }, "backgroundColorCropType": "OuterArea", "backgroundImageCropType": "MiddleArea", "left": 2, "top": 2, "width": 200, "height": 150, "locationMeasureType": "Pixels", "sizeMeasureType": "Pixels", "rotationAngle": 0, "horizontalAlignment": "Left", "verticalAlignment": "Top", "margin": { "all": 10, "left": 10, "top": 10, "right": 10, "bottom": 10 }, "marginMeasureType": "Pixels", "opacity": 1.0, "signAllPages": false, "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [ 1 ] }, "OptionsType": "ImagesSignStampOptionsData" }'
 ```




 Response

```html 
{
  "fileName": "01_pages.png",
  "folder": "Output",
  "Code": 200,
  "Status" : "OK"
}
 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Add Stamp Signature to Document at specified URL ###




 C#




{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Signature_Stamp_URL.cs >}}







 PHP




{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_Stamp_URL.php >}}







 Java




{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Signature_Stamp_URL.java >}}







 Python




{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Signature_Stamp_URL.py >}}







 Ruby




{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Signature_Signature_Stamp_URL.rb >}}






 

# Setup Background Brush for Stamp Signatures #

You can creates Text Signature for document with [signature-options-objects]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}). Signature Stamp Options and all inherited classes have been updated in (Release 18.7) with newly added property** BackgroundBrush** which support following brush types:

 



 Linear Gradient Brush
\\



**Brush Style option**

```html 

"backgroundBrush": {"startColor": {"web": "CornflowerBlue"}, "endColor": {"web": "DarkBlue"}, "angle": 0.0, "brushType": "LinearGradientBrush"}


 ```





 



 Radial Gradient Brush
\\



**Brush Style option**

```html 

"backgroundBrush": { "innerColor": {"web": "CornflowerBlue"}, "outerColor": {"web": "DarkBlue"}, "brushType": "RadialGradientBrush"}


 ```





 



 Solid Brush
\\



**Brush Style option**

```html 

"backgroundBrush": {"color": {"web": "DarkBlue"}, "brushType": "SolidBrush"}


 ```





 



 Texture Brush
\\



**Brush Style option**

```html 

"backgroundBrush": {"imageGuid": "images\signature_01.jpg", "brushType": "TextureBrush"}


 ```







## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add Text signature to a document](https://apireference.groupdocs.cloud/signature/#!/Signing/PostText).

## cURL Example ##





 Request

```html 
curl --request POST \
--url http://api.groupdocs.cloud/v1/signature/01_pages.pptx/stamp?folder#storage \
--header 'authorization: [Access Token]' \
--header 'content-type: application/json' \
--data '{ "outerLines": [ { "height": 20, "backgroundColor": { "Web": "BlueViolet" }, "text": " * John Smith * ", "font": { "fontFamily": "Arial", "fontSize": 12.0, "bold": true, "italic": true, "underline": false }, "textColor": { "Web": "DarkOrange" }, "textBottomIntent": 5, "textRepeatType": "FullTextRepeat", "outerBorder": { "style": "Default", "transparency": 0.7, "weight": 2.0, "color": {  "Web": "DarkOrange" } }, "innerBorder": { "style": "Default", "transparency": 0.5, "weight": 2.0, "color": {  "Web": "DarkOrange" } }, "visible": true } ], "innerLines": [ { "height": 30, "backgroundColor": { "Web": "Transparent", "Alpha": 0 }, "text": "John Smith", "font": { "fontFamily": "Times New Roman", "fontSize": 20.0, "bold": true, "italic": true, "underline": false }, "textColor": { "Web": "Gold" }, "textBottomIntent": 3, "textRepeatType": "None", "visible": true } ], "backgroundColor": { "Web": "CornflowerBlue" }, "backgroundBrush": { "startColor": { "web": "LightBlue" }, "endColor": { "web": "DarkBlue" }, "angle": 45.0, "brushType": "LinearGradientBrush" }, "backgroundColorCropType": "OuterArea", "backgroundImageCropType": "MiddleArea", "left": 2, "top": 2, "width": 200, "height": 150, "locationMeasureType": "Pixels", "sizeMeasureType": "Pixels", "rotationAngle": 0, "horizontalAlignment": "Left", "verticalAlignment": "Top", "margin": { "all": 10, "left": 10, "top": 10, "right": 10, "bottom": 10 }, "marginMeasureType": "Pixels", "opacity": 1.0, "signAllPages": false, "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [ 1 ] }, "OptionsType": "SlidesSignStampOptionsData" }'
 ```




 Response

```html 
{
  "fileName": "01_pages.pptx",
  "folder": "Output",
  "Code": 200,
  "Status" : "OK"
}
 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Setup Background Brush for Stamp Signatures ###





 C#




{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Signature_Stamp_Background_Brush.cs >}}







 PHP




{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_Stamp_Background_Brush.php >}}







 Java




{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Signature_Stamp_Background_Brush.java >}}







 Python




{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Signature_Stamp_Background_Brush.py >}}







 Ruby




{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Signature_Signature_Stamp_Background_Brush.rb >}}






