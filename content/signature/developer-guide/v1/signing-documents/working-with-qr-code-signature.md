---
id: "working-with-qr-code-signature"
url: "signature/working-with-qr-code-signature"
title: "Working with QR Code Signature"
productName: "GroupDocs.Signature Cloud"
weight: 4
description: ""
keywords: ""
---

{{< alert style="info" >}}
Note:  The features listed on this page are supported only in GroupDocs.Signature Cloud V1
{{< /alert >}}

# Introduction #

GroupDocs.Signature Cloud REST API supports to sign a document with QRCode. It provides methods to create QRCode Signature in Document Pages with different options of QRCode type, location, alignment, font, margins and appearances by using [Signature Options Object]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}) data in request body.

# Add QRCode Signature to Document #

You can create QRCode Signature on Document provided by fileName and document folder (if required) using following API. It expects [Signature Options Object]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}) data in request body.

It returns an object which contains document name, folder location and command status.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add QRCode signature to a document](https://apireference.groupdocs.cloud/signature/#!/Signing/PostQRCode).

## cURL Example ##

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}} {{< tab tabNum="1" >}}

```javascript
curl -v "https://api.groupdocs.cloud/v1/signature/one-page.docx/qrcode" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" -d "{"QRCodeTypeName": "Aztec","BorderVisiblity" : true,"BorderDashStyle" : "DashDotDot","BorderWeight" : 1,"Opacity" : 0.5,"Margin": {"All": 0,"Left": 0,"Top": 0,"Right": 0,"Bottom": 0},"SheetNumber": 1,"RowNumber": 11,"ColumnNumber": 22,"BorderVisiblity": true,"BorderDashStyle": 5,"BorderTransparency": 0.0,"BorderWeight": 1.0,"BackgroundTransparency": 0.1,"SignatureImplementation": "TextStamp","Text": "John Smith","Width": 100,"Height": 100,"LocationMeasureType": "Pixels","SizeMeasureType": "Pixels","RotationAngle": 0,"HorizontalAlignment": "Right","VerticalAlignment": "Center","MarginMeasureType": "Pixels","SignAllPages": false,"Font": {"FontFamily": "Times New Roman","FontSize": 14.0,"Bold": false,"Italic": false,"Underline": false},"ForeColor": {"Web": "Black"},"BorderColor": {"Web": "Black"},"BackgroundColor": {"Web": "OrangeRed"},"OptionsType": "WordsSignQRCodeOptionsData"}" \
-H "authorization: Bearer rf1Wyp3-Cz_xukjKqvzF-OMwYvhJcl0rJ6CQ0IgQbZwdSGTKYJziBpGNeDdzGSwwXgsRLCCfPLhHJBKPv8dzqX3tGA8n8SA4tXhLdnGh-hws2gQgmCWEjF0RpzEdJA6jh6tGZyOSAa2GlTrLhuflBwjMB5-dc8JwRmI-ssOiXkO3fSRxnwWuWih24Co8-n8elsun4HxZVMqCzXepAiXBV9UBeUktV_PLclri_lTJEnDzoJRzfRyDigjb2-luODo9aX8DFseboggoCIMKDoyLPSVHnFXgs5EWV2aQ_DgRm_D6UPn2T1Gn7OAIe-T8aA7ypDCoR-wuTJdB8o7T0f2I8K-8FrXCy2Sgb8B5QPpAOcLdiBBqFxRdk8f2c67J-rSbm2WUPWK65pbLa8NGHHdIRKuiI87NmphWuKc39a_zcgEg4MnHSlDeephmStnLS8OayQObNdLQBYAmoeQeVpZRy9t9bcU"
```

{{< /tab >}} {{< tab tabNum="2" >}}

```javascript
{
  "fileName": "one-page.docx",
  "folder": "Output",
  "code": 200,
  "status": "OK"
}
{{< /tab >}} {{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Add QRCode Signature to Document ###

{{< tabs tabTotal="5" tabID="10" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Python" tabName5="Ruby" >}} {{< tab tabNum="1" >}}

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Signature_QRCode.cs >}}

{{< /tab >}} {{< tab tabNum="3" >}}

{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_QRCode.php >}}

{{< /tab >}} {{< tab tabNum="2" >}}

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Signature_QRCode.java >}}

{{< /tab >}} {{< tab tabNum="4" >}}

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Signature_QRCode.py >}}

{{< /tab >}} {{< tab tabNum="5" >}}

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Signature_QRCode.rb >}}

{{< /tab >}} {{< /tabs >}}

# Add QRCode Signature to Document at Provided URL #

You can creates QRCode Signature for document at provided URL with [signature-options-objects]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}). It retrieves file from specified URL and tries to detect file type when fileName parameter is not specified. It saves retrieved file in storage, by using fileName and folder parameters to specify desired file name and folder to save file. When file with specified name already exists in storage new unique file name will be used for file. It expects [Signature Options Object]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}) data in request body and returns object which contains document name and folder location.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add QRCode signature to a document at provided URL](https://apireference.groupdocs.cloud/signature/#!/Signing/PostQRCodeFromUrl).

## cURL Example ##

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}} {{< tab tabNum="1" >}}

```javascript
curl -v "https://api.groupdocs.cloud/v1/signature/qrcode?url#https%3A%2F%2Fwww.dropbox.com%2Fs%2Fbzx1xm68zd0c910%2FPieChart.docx" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d "{"QRCodeTypeName": "Aztec","BorderVisiblity" : true,"BorderDashStyle" : "DashDotDot","BorderWeight" : 1,"Opacity" : 0.5,"Margin": {"All": 0,"Left": 0,"Top": 0,"Right": 0,"Bottom": 0},"SheetNumber": 1,"RowNumber": 11,"ColumnNumber": 22,"BorderVisiblity": true,"BorderDashStyle": 5,"BorderTransparency": 0.0,"BorderWeight": 1.0,"BackgroundTransparency": 0.1,"SignatureImplementation": "TextStamp","Text": "John Smith","Width": 100,"Height": 100,"LocationMeasureType": "Pixels","SizeMeasureType": "Pixels","RotationAngle": 0,"HorizontalAlignment": "Right","VerticalAlignment": "Center","MarginMeasureType": "Pixels","SignAllPages": false,"Font": {"FontFamily": "Times New Roman","FontSize": 14.0,"Bold": false,"Italic": false,"Underline": false},"ForeColor": {"Web": "Black"},"BorderColor": {"Web": "Black"},"BackgroundColor": {"Web": "OrangeRed"},"OptionsType": "WordsSignQRCodeOptionsData"}" \
-H "authorization: Bearer rf1Wyp3-Cz_xukjKqvzF-OMwYvhJcl0rJ6CQ0IgQbZwdSGTKYJziBpGNeDdzGSwwXgsRLCCfPLhHJBKPv8dzqX3tGA8n8SA4tXhLdnGh-hws2gQgmCWEjF0RpzEdJA6jh6tGZyOSAa2GlTrLhuflBwjMB5-dc8JwRmI-ssOiXkO3fSRxnwWuWih24Co8-n8elsun4HxZVMqCzXepAiXBV9UBeUktV_PLclri_lTJEnDzoJRzfRyDigjb2-luODo9aX8DFseboggoCIMKDoyLPSVHnFXgs5EWV2aQ_DgRm_D6UPn2T1Gn7OAIe-T8aA7ypDCoR-wuTJdB8o7T0f2I8K-8FrXCy2Sgb8B5QPpAOcLdiBBqFxRdk8f2c67J-rSbm2WUPWK65pbLa8NGHHdIRKuiI87NmphWuKc39a_zcgEg4MnHSlDeephmStnLS8OayQObNdLQBYAmoeQeVpZRy9t9bcU" 
```

{{< /tab >}} {{< tab tabNum="2" >}}

```javascript
{
  "fileName": "PieChart.docx",
  "folder": "Output",
  "Code": 200,
  "Status" : "OK"
}
{{< /tab >}} {{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Add QRCode Signature to Document at specified URL ###

{{< tabs tabTotal="5" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Python" tabName5="Ruby" >}} {{< tab tabNum="1" >}}

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Signature_QRCode_URL.cs >}}

{{< /tab >}} {{< tab tabNum="3" >}}

{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_QRCode_URL.php >}}

{{< /tab >}} {{< tab tabNum="2" >}}

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Signature_QRCode_URL.java >}}

{{< /tab >}} {{< tab tabNum="4" >}}

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Signature_QRCode_URL.py >}}

{{< /tab >}} {{< tab tabNum="5" >}}

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Signature_QRCode_URL.rb >}}

{{< /tab >}} {{< /tabs >}}

## Setup QR-Code Logo image (Signature QR-Code Options) ##

You can creates QRCode Signature for document at provided [signature-options-objects]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}). Signature QR-Code Options have been updated in (Release 18.7) with newly added property** LogoGuid **which support QR-Code background image located at the center of QR-Code. To put QRCode Signature to Image Document (png, jpeg, gif, tiff and another file formats) Signature provides new options **[ImagesSignQRCodeOptionsData](https://docs.dynabic.com/display/signaturecloud/Signature+Options+Objects#SignatureOptionsObjects-ImagesSignQRCodeOptionsDataObject)** that specify text, signature area, alignment, appearance, colors and another render features.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add QRCode signature to a document](https://apireference.groupdocs.cloud/signature/#!/Signing/PostStamp).

## cURL Example ##

{{< tabs tabTotal="2" tabID="3" tabName1="Request" tabName2="Response" >}} {{< tab tabNum="1" >}}

```javascript
curl --request POST \--url http://api.groupdocs.cloud/v1/signature/01_pages.png/qrcode?folder#storage \--header 'authorization: [Access Token]' \--header 'content-type: application/json' \--data '{ "qrCodeTypeName": "Aztec", "borderVisiblity": true, "borderDashStyle": "Solid", "borderWeight": 1.0, "opacity": 0.8, "text": "123456789012", "left": 2, "top": 2, "width": 200, "height": 100, "locationMeasureType": "Pixels", "sizeMeasureType": "Pixels", "stretch": "None", "rotationAngle": 0, "horizontalAlignment": "Left", "logoGuid": "images/logo1.png""verticalAlignment": "Top", "margin": { "all": 10, "left": 10, "top": 10, "right": 10, "bottom": 10 }, "marginMeasureType": "Pixels", "signAllPages": false, "font": { "fontFamily": "Times New Roman", "fontSize": 14.0, "bold": false, "italic": false, "underline": false }, "foreColor": { "Web": "Black" }, "borderColor": { "Web": "Black" }, "backgroundColor": { "Web": "Transparent", "Alpha": 0 }, "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [ 1 ] }, "OptionsType": "ImagesSignQRCodeOptionsData" }'
```

{{< /tab >}} {{< tab tabNum="2" >}}

```javascript
{
  "fileName": "01_pages.png",
  "folder": "Output",
  "Code": 200,
  "Status" : "OK"
}
{{< /tab >}} {{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Setup QR-Code Logo image (Signature QR-Code Options) ###

{{< tabs tabTotal="5" tabID="12" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Python" tabName5="Ruby" >}} {{< tab tabNum="1" >}}

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Signature_QRCode_URL.cs >}}

{{< /tab >}} {{< tab tabNum="3" >}}

{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_QRCode_URL.php >}}

{{< /tab >}} {{< tab tabNum="2" >}}

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Signature_QRCode_URL.java >}}

{{< /tab >}} {{< tab tabNum="4" >}}

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Signature_QRCode_URL.py >}}

{{< /tab >}} {{< tab tabNum="5" >}}

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Signature_QRCode_URL.rb >}}

{{< /tab >}} {{< /tabs >}}

# Add QRCode Signature to Document at Provided URL #

You can creates QRCode Signature for document at provided URL with [signature-options-objects]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}). It retrieves file from specified URL and tries to detect file type when fileName parameter is not specified. It saves retrieved file in storage, by using fileName and folder parameters to specify desired file name and folder to save file. When file with specified name already exists in storage new unique file name will be used for file. It expects [Signature Options Object]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}) data in request body and returns object which contains document name and folder location.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add QRCode signature to a document at provided URL](https://apireference.groupdocs.cloud/signature/#!/Signing/PostQRCodeFromUrl).

## cURL Example ##

{{< tabs tabTotal="2" tabID="4" tabName1="Request" tabName2="Response" >}} {{< tab tabNum="1" >}}

```javascript
curl -v "https://api.groupdocs.cloud/v1/signature/qrcode?url#https%3A%2F%2Fwww.dropbox.com%2Fs%2Fbzx1xm68zd0c910%2FPieChart.docx" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d "{"QRCodeTypeName": "Aztec","BorderVisiblity" : true,"BorderDashStyle" : "DashDotDot","BorderWeight" : 1,"Opacity" : 0.5,"Margin": {"All": 0,"Left": 0,"Top": 0,"Right": 0,"Bottom": 0},"SheetNumber": 1,"RowNumber": 11,"ColumnNumber": 22,"BorderVisiblity": true,"BorderDashStyle": 5,"BorderTransparency": 0.0,"BorderWeight": 1.0,"BackgroundTransparency": 0.1,"SignatureImplementation": "TextStamp","Text": "John Smith","Width": 100,"Height": 100,"LocationMeasureType": "Pixels","SizeMeasureType": "Pixels","RotationAngle": 0,"HorizontalAlignment": "Right","VerticalAlignment": "Center","MarginMeasureType": "Pixels","SignAllPages": false,"Font": {"FontFamily": "Times New Roman","FontSize": 14.0,"Bold": false,"Italic": false,"Underline": false},"ForeColor": {"Web": "Black"},"BorderColor": {"Web": "Black"},"BackgroundColor": {"Web": "OrangeRed"},"OptionsType": "WordsSignQRCodeOptionsData"}" \
-H "authorization: Bearer rf1Wyp3-Cz_xukjKqvzF-OMwYvhJcl0rJ6CQ0IgQbZwdSGTKYJziBpGNeDdzGSwwXgsRLCCfPLhHJBKPv8dzqX3tGA8n8SA4tXhLdnGh-hws2gQgmCWEjF0RpzEdJA6jh6tGZyOSAa2GlTrLhuflBwjMB5-dc8JwRmI-ssOiXkO3fSRxnwWuWih24Co8-n8elsun4HxZVMqCzXepAiXBV9UBeUktV_PLclri_lTJEnDzoJRzfRyDigjb2-luODo9aX8DFseboggoCIMKDoyLPSVHnFXgs5EWV2aQ_DgRm_D6UPn2T1Gn7OAIe-T8aA7ypDCoR-wuTJdB8o7T0f2I8K-8FrXCy2Sgb8B5QPpAOcLdiBBqFxRdk8f2c67J-rSbm2WUPWK65pbLa8NGHHdIRKuiI87NmphWuKc39a_zcgEg4MnHSlDeephmStnLS8OayQObNdLQBYAmoeQeVpZRy9t9bcU" 
```

{{< /tab >}} {{< tab tabNum="2" >}}

```javascript
{
  "fileName": "PieChart.docx",
  "folder": "Output",
  "Code": 200,
  "Status" : "OK"
}
{{< /tab >}} {{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Add QRCode Signature to Document at specified URL ###

{{< tabs tabTotal="5" tabID="13" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Python" tabName5="Ruby" >}} {{< tab tabNum="1" >}}

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Signature_QRCode_URL.cs >}}

{{< /tab >}} {{< tab tabNum="3" >}}

{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_QRCode_URL.php >}}

{{< /tab >}} {{< tab tabNum="2" >}}

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Signature_QRCode_URL.java >}}

{{< /tab >}} {{< tab tabNum="4" >}}

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Signature_QRCode_URL.py >}}

{{< /tab >}} {{< tab tabNum="5" >}}

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Signature_QRCode_URL.rb >}}

{{< /tab >}} {{< /tabs >}}

