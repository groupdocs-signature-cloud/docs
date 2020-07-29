---
id: "working-with-signing-document"
url: "signature/working-with-signing-document"
title: "Working with Signing Document"
productName: "GroupDocs.Signature Cloud"
weight: 1
description: ""
keywords: ""
---






# Add Barcode Signature to Document #

GroupDocs.Signature Cloud REST API supports to sign a document with Barcode. It provides methods to create Barcode Signature in Document Pages with different options of Barcode type, location, alignment, font, margins, and appearances by using [Signature Options Objects]({{< ref "signature/developer-guide/data-structures/common-structures.md" >}})) data in the request body.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add a Barcode signature to a document](https://apireference.groupdocs.cloud/signature/#/Sign/CreateSignatures).

## cURL Example ##





 Request

```html 
curl -X POST "https://api.groupdocs.cloud/v2.0/signature/create" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]" -H  "Content-Type: application/json" -d "{  \"FileInfo\": {    \"FilePath\": \"one-page.docx\",    \"StorageName\": \"MyStorage\",    \"VersionId\": \"\",    \"Password\": \"\"  },  \"SaveOptions\": {    \"OverwriteExisting\": true,    \"OutputFilePath\": \"result-one-page.docx\",    \"SaveFormat\": \"docx\"  },  \"SignOptions\": [    {  \"DocumentType\": \"WordProcessing\",  \"SignatureType\": \"Barcode\",    \"Page\": 1,  \"AllPages\": false,  \"PagesSetup\": {    \"FirstPage\": false,    \"LastPage\": true,    \"OddPages\": false,    \"EvenPages\": true,    \"PageNumbers\": [1]  },  \"Text\": \"John Smith\",  \"BarcodeType\": \"Code128\",  \"Left\": 2,  \"Top\": 2,  \"Width\": 200,  \"Height\": 100,  \"Stretch\": \"None\",  \"RotationAngle\": 45,  \"HorizontalAlignment\": \"Left\",  \"VerticalAlignment\": \"Center\",  \"LocationMeasureType\": \"Pixels\",  \"SizeMeasureType\": \"Pixels\",  \"Margin\": {    \"All\": 5,    \"Left\": 5,    \"Top\": 5,    \"Right\": 5,    \"Bottom\": 5  },  \"MarginMeasureType\": \"Pixels\",  \"Font\": {    \"FontFamily\": \"Times New Roman\",    \"FontSize\": 14.0,    \"Bold\": false,    \"Italic\": false,    \"Underline\": false  },  \"ForeColor\": {    \"Web\": \"DarkOrange\"  },  \"BorderColor\": {    \"Web\": \"DarkOrange\",    \"Alpha\": \"20\",  },  \"BackgroundBrush\":   {      \"Color\": {\"Web\": \"DarkBlue\"},      \"BrushType\": \"SolidBrush\"  },  \"BorderVisiblity\": true,  \"BorderDashStyle\": \"Dash\",  \"BorderTransparency\": 0.55,  \"BorderWeight\": 12.0,  \"BackgroundTransparency\": 0.8,  \"TextHorizontalAlignment\": \"Left\",  \"TextVerticalAlignment\": \"Top\",  \"Opacity\": 0.5,  \"CodeTextAlignment\": \"Below\",  \"InnerMargins\": {    \"All\": 5,    \"Left\": 5,    \"Top\": 5,    \"Right\": 5,    \"Bottom\": 5  },}   ]}"


 ```




 Response

```html 
{
  "FileInfo": {
    "FilePath": "files01.docx"
  },
  "Size" : 12345,
  "DownloadUrl": "signed/ofiles01.docx"
}


 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Add Barcode Signature to Document ###





 C#




{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Barcode_Signature.cs >}}







 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Barcode_Signature.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Barcode_Signature.php >}}







 Ruby




{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Barcode_Signature.rb >}}







 Node




{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Barcode_Signature.js >}}







 Python




{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Barcode_Signature.py >}}









# Add Digital Signature to Document #

GroupDocs.Signature Cloud REST API supports to add Digital Signature to a document. It provides methods to create Digital Signature in Document Pages with different options of Certificate type, location, alignment, font, margins, and appearances by using [Signature Options Object]({{< ref "signature/developer-guide/data-structures/common-structures.md" >}})) data in the request body.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add a Digital signature to a document](https://apireference.groupdocs.cloud/signature/#/Sign/CreateSignatures).

## cURL Example ##





 Request

```html 
curl -X POST "https://api.groupdocs.cloud/v2.0/signature/create" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]" -H  "Content-Type: application/json" -d "{  \"FileInfo\": {    \"FilePath\": \"one-page.docx\",    \"StorageName\": \"MyStorage\",    \"VersionId\": \"\",    \"Password\": \"\"  },  \"SaveOptions\": {    \"OverwriteExisting\": true,    \"OutputFilePath\": \"result-one-page.docx\",    \"SaveFormat\": \"docx\"  },  \"SignOptions\": [    {  \"DocumentType\": \"WordProcessing\",  \"SignatureType\": \"Digital\",    \"Page\": 1,  \"AllPages\": false,  \"PagesSetup\": {    \"FirstPage\": false,    \"LastPage\": true,    \"OddPages\": false,    \"EvenPages\": true,    \"PageNumbers\": [1]  },  \"Text\": \"John Smith\",  \"BarcodeType\": \"CryptoApi\",  \"Left\": 2,  \"Top\": 2,  \"Width\": 200,  \"Height\": 100,  \"Stretch\": \"None\",  \"RotationAngle\": 45,  \"HorizontalAlignment\": \"Left\",  \"VerticalAlignment\": \"Center\",  \"LocationMeasureType\": \"Pixels\",  \"SizeMeasureType\": \"Pixels\",  \"Margin\": {    \"All\": 5,    \"Left\": 5,    \"Top\": 5,    \"Right\": 5,    \"Bottom\": 5  },  \"MarginMeasureType\": \"Pixels\",  \"Font\": {    \"FontFamily\": \"Times New Roman\",    \"FontSize\": 14.0,    \"Bold\": false,    \"Italic\": false,    \"Underline\": false  },  \"ForeColor\": {    \"Web\": \"DarkOrange\"  },  \"BorderColor\": {    \"Web\": \"DarkOrange\",    \"Alpha\": \"20\",  },  \"BackgroundBrush\":   {      \"Color\": {\"Web\": \"DarkBlue\"},      \"BrushType\": \"SolidBrush\"  },  \"BorderVisiblity\": true,  \"BorderDashStyle\": \"Dash\",  \"BorderTransparency\": 0.55,  \"BorderWeight\": 12.0,  \"BackgroundTransparency\": 0.8,  \"TextHorizontalAlignment\": \"Left\",  \"TextVerticalAlignment\": \"Top\",  \"Opacity\": 0.5,  \"CodeTextAlignment\": \"Below\",  \"InnerMargins\": {    \"All\": 5,    \"Left\": 5,    \"Top\": 5,    \"Right\": 5,    \"Bottom\": 5  },}   ]}"


 ```




 Response

```html 
{
  "FileInfo": {
    "FilePath": "one-page.docx"
  },
  "Size" : 12345,
  "DownloadUrl": "signed/one-page.docx"
}


 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Add Digital Signature to Document ###





 C#




{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Digital_Signature.cs >}}







 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Digital_Signature.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Digital_Signature.php >}}







 Ruby




{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Digital_Signature.rb >}}







 Node




{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Digital_Signature.js >}}







 Python




{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Digital_Signature.py >}}









# Add Image Signature to Document #

GroupDocs.Signature Cloud REST API supports to sign a document with Image. It provides methods to create Image Signature in Document Pages with different options of the Image name, location, alignment, font, margins, and appearances by using [Signature Options Objects]({{< ref "signature/developer-guide/data-structures/common-structures.md" >}})) object data in the request body.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add an Image signature to a document](https://apireference.groupdocs.cloud/signature/#/Sign/CreateSignatures).

## cURL Example ##





 Request

```html 
curl -X POST "https://api.groupdocs.cloud/v2.0/signature/create" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]" -H  "Content-Type: application/json" -d "{  \"FileInfo\": {    \"FilePath\": \"one-page.docx\",    \"StorageName\": \"MyStorage\",    \"VersionId\": \"\",    \"Password\": \"\"  },  \"SaveOptions\": {    \"OverwriteExisting\": true,    \"OutputFilePath\": \"result-one-page.docx\",    \"SaveFormat\": \"docx\"  },  \"SignOptions\": [    {  \"DocumentType\": \"WordProcessing\",  \"SignatureType\": \"Image\",    \"Page\": 1,  \"AllPages\": false,  \"PagesSetup\": {    \"FirstPage\": false,    \"LastPage\": true,    \"OddPages\": false,    \"EvenPages\": true,    \"PageNumbers\": [1]  },  \"Text\": \"John Smith\",  \"Left\": 2,  \"Top\": 2,  \"Width\": 200,  \"Height\": 100,  \"Stretch\": \"None\",  \"RotationAngle\": 45,  \"HorizontalAlignment\": \"Left\",  \"VerticalAlignment\": \"Center\",  \"LocationMeasureType\": \"Pixels\",  \"SizeMeasureType\": \"Pixels\",  \"Margin\": {    \"All\": 5,    \"Left\": 5,    \"Top\": 5,    \"Right\": 5,    \"Bottom\": 5  },  \"MarginMeasureType\": \"Pixels\",  \"Font\": {    \"FontFamily\": \"Times New Roman\",    \"FontSize\": 14.0,    \"Bold\": false,    \"Italic\": false,    \"Underline\": false  },  \"ForeColor\": {    \"Web\": \"DarkOrange\"  },  \"BorderColor\": {    \"Web\": \"DarkOrange\",    \"Alpha\": \"20\",  },  \"BackgroundBrush\":   {      \"Color\": {\"Web\": \"DarkBlue\"},      \"BrushType\": \"SolidBrush\"  },  \"BorderVisiblity\": true,  \"BorderDashStyle\": \"Dash\",  \"BorderTransparency\": 0.55,  \"BorderWeight\": 12.0,  \"BackgroundTransparency\": 0.8,  \"TextHorizontalAlignment\": \"Left\",  \"TextVerticalAlignment\": \"Top\",  \"Opacity\": 0.5,  \"CodeTextAlignment\": \"Below\",  \"InnerMargins\": {    \"All\": 5,    \"Left\": 5,    \"Top\": 5,    \"Right\": 5,    \"Bottom\": 5  },}   ]}"


 ```




 Response

```html 
{
  "FileInfo": {
    "FilePath": "one-page.docx"
  },
  "Size" : 12345,
  "DownloadUrl": "signed/one-page.docx"
}

 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Add Image Signature to Document ###





 C#




{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Image_Signature.cs >}}







 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Image_Signature.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Image_Signature.php >}}







 Ruby




{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Image_Signature.rb >}}







 Node




{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Image_Signature.js >}}







 Python




{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Image_Signature.py >}}









# Add QRCode Signature to Document #

GroupDocs.Signature Cloud REST API supports to sign a document with QRCode. It provides methods to create QRCode Signature in Document Pages with different options of QRCode type, location, alignment, font, margins, and appearances by using [Signature Options Object]({{< ref "signature/developer-guide/data-structures/common-structures.md" >}})) data in the request body.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add QRCode signature to a document](https://apireference.groupdocs.cloud/signature/#/Sign/CreateSignatures).

## cURL Example ##





 Request

```html 
curl -X POST "https://api.groupdocs.cloud/v2.0/signature/create" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]" -H  "Content-Type: application/json" -d "{  \"FileInfo\": {    \"FilePath\": \"one-page.docx\",    \"StorageName\": \"MyStorage\",    \"VersionId\": \"\",    \"Password\": \"\"  },  \"SaveOptions\": {    \"OverwriteExisting\": true,    \"OutputFilePath\": \"result-one-page.docx\",    \"SaveFormat\": \"docx\"  },  \"SignOptions\": [    {  \"DocumentType\": \"WordProcessing\",  \"SignatureType\": \"QRCode\",    \"Page\": 1,  \"AllPages\": false,  \"PagesSetup\": {    \"FirstPage\": false,    \"LastPage\": true,    \"OddPages\": false,    \"EvenPages\": true,    \"PageNumbers\": [1]  },  \"Text\": \"John Smith\",  ,  \"Left\": 2,  \"Top\": 2,  \"Width\": 200,  \"Height\": 100,  \"Stretch\": \"None\",  \"RotationAngle\": 45,  \"HorizontalAlignment\": \"Left\",  \"VerticalAlignment\": \"Center\",  \"LocationMeasureType\": \"Pixels\",  \"SizeMeasureType\": \"Pixels\",  \"Margin\": {    \"All\": 5,    \"Left\": 5,    \"Top\": 5,    \"Right\": 5,    \"Bottom\": 5  },  \"MarginMeasureType\": \"Pixels\",  \"Font\": {    \"FontFamily\": \"Times New Roman\",    \"FontSize\": 14.0,    \"Bold\": false,    \"Italic\": false,    \"Underline\": false  },  \"ForeColor\": {    \"Web\": \"DarkOrange\"  },  \"BorderColor\": {    \"Web\": \"DarkOrange\",    \"Alpha\": \"20\",  },  \"BackgroundBrush\":   {      \"Color\": {\"Web\": \"DarkBlue\"},      \"BrushType\": \"SolidBrush\"  },  \"BorderVisiblity\": true,  \"BorderDashStyle\": \"Dash\",  \"BorderTransparency\": 0.55,  \"BorderWeight\": 12.0,  \"BackgroundTransparency\": 0.8,  \"TextHorizontalAlignment\": \"Left\",  \"TextVerticalAlignment\": \"Top\",  \"Opacity\": 0.5,  \"CodeTextAlignment\": \"Below\",  \"InnerMargins\": {    \"All\": 5,    \"Left\": 5,    \"Top\": 5,    \"Right\": 5,    \"Bottom\": 5  },}   ]}"
 ```




 Response

```html 
{
  "FileInfo": {
    "FilePath": "one-page.docx"
  },
  "Size" : 12345,
  "DownloadUrl": "signed/one-page.docx"
}
 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Add QRCode Signature to Document ###





 C#




{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_QRCode_Signature.cs >}}







 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_QRCode_Signature.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_QRCode_Signature.php >}}







 Ruby




{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_QRCode_Signature.rb >}}







 Node




{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_QRCode_Signature.js >}}







 Python




{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_QRCode_Signature.py >}}









# Add Stamp Signature to Document #

GroupDocs.Signature Cloud REST API supports to put Stamp Signature on the supported file format. It provides methods to create Stamp Signature in Document Pages with different options to add an image as a stamp, location, alignment, font, margins, and appearances by using [Signature Options Object]({{< ref "signature/developer-guide/data-structures/common-structures.md" >}})) data in the request body.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add Stamp signature to a document](https://apireference.groupdocs.cloud/signature/#/Sign/CreateSignatures).

## cURL Example ##





 Request

curl -X POST "https://api.groupdocs.cloud/v2.0/signature/create" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]" -H  "Content-Type: application/json" -d "{  \"FileInfo\": {    \"FilePath\": \"one-page.docx\",    \"StorageName\": \"MyStorage\",    \"VersionId\": \"\",    \"Password\": \"\"  },  \"SaveOptions\": {    \"OverwriteExisting\": true,    \"OutputFilePath\": \"result-one-page.docx\",    \"SaveFormat\": \"docx\"  },  \"SignOptions\": [    {  \"DocumentType\": \"WordProcessing\",  \"SignatureType\": \"Stamp\",    \"Page\": 1,  \"AllPages\": false,  \"PagesSetup\": {    \"FirstPage\": false,    \"LastPage\": true,    \"OddPages\": false,    \"EvenPages\": true,    \"PageNumbers\": [1]  },  \"Text\": \"John Smith\", \"Left\": 2,  \"Top\": 2,  \"Width\": 200,  \"Height\": 100,  \"Stretch\": \"None\",  \"RotationAngle\": 45,  \"HorizontalAlignment\": \"Left\",  \"VerticalAlignment\": \"Center\",  \"LocationMeasureType\": \"Pixels\",  \"SizeMeasureType\": \"Pixels\",  \"Margin\": {    \"All\": 5,    \"Left\": 5,    \"Top\": 5,    \"Right\": 5,    \"Bottom\": 5  },  \"MarginMeasureType\": \"Pixels\",  \"Font\": {    \"FontFamily\": \"Times New Roman\",    \"FontSize\": 14.0,    \"Bold\": false,    \"Italic\": false,    \"Underline\": false  },  \"ForeColor\": {    \"Web\": \"DarkOrange\"  },  \"BorderColor\": {    \"Web\": \"DarkOrange\",    \"Alpha\": \"20\",  },  \"BackgroundBrush\":   {      \"Color\": {\"Web\": \"DarkBlue\"},      \"BrushType\": \"SolidBrush\"  },  \"BorderVisiblity\": true,  \"BorderDashStyle\": \"Dash\",  \"BorderTransparency\": 0.55,  \"BorderWeight\": 12.0,  \"BackgroundTransparency\": 0.8,  \"TextHorizontalAlignment\": \"Left\",  \"TextVerticalAlignment\": \"Top\",  \"Opacity\": 0.5,  \"CodeTextAlignment\": \"Below\",  \"InnerMargins\": {    \"All\": 5,    \"Left\": 5,    \"Top\": 5,    \"Right\": 5,    \"Bottom\": 5  },}   ]}"






 Response

```html 
{
  "FileInfo": {
    "FilePath": "one-page.docx"
  },
  "Size" : 12345,
  "DownloadUrl": "signed/one-page.docx"
}
 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Add Stamp Signature to Document ###





 C#




{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Stamp_Signature.cs >}}







 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Stamp_Signature.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Stamp_Signature.php >}}







 Ruby




{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_QRCode_Signature.rb >}}







 Node




{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Stamp_Signature.js >}}







 Python




{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Stamp_Signature.py >}}









# Add Text Signature to Document #

GroupDocs.Signature Cloud REST API supports to sign a document with Text. It provides methods to create Text Signature in Document Pages with different options of Text, location, alignment, font, margins, and appearances by using [Signature Options Object]({{< ref "signature/developer-guide/data-structures/common-structures.md" >}})) data in the request body.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add Text signature to a document](https://apireference.groupdocs.cloud/signature/#/Sign/CreateSignatures).

## cURL Example ##





 Request

```html 
curl -v "https://api.groupdocs.cloud/v2/signature/one-page.docx/text" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d "{"Margin": {"All": 0,"Left": 0,"Top": 0,"Right": 0,"Bottom": 0},"SheetNumber": 1,"RowNumber": 11,"ColumnNumber": 22,"BorderVisiblity": true,"BorderDashStyle": 5,"BorderTransparency": 0.0,"BorderWeight": 1.0,"BackgroundTransparency": 0.1,"SignatureImplementation": "TextStamp","Text": "John Smith","Width": 100,"Height": 100,"LocationMeasureType": "Pixels","SizeMeasureType": "Pixels","RotationAngle": 0,"HorizontalAlignment": "Right","VerticalAlignment": "Center","MarginMeasureType": "Pixels","SignAllPages": false,"Font": {"FontFamily": "Times New Roman","FontSize": 14.0,"Bold": false,"Italic": false,"Underline": false},"ForeColor": {"Web": "Black"},"BorderColor": {"Web": "Black"},"BackgroundColor": {"Web": "OrangeRed"},"OptionsType": "WordsSignTextOptionsData"}" \
-H "authorization: Bearer rf1Wyp3-Cz_xukjKqvzF-OMwYvhJcl0rJ6CQ0IgQbZwdSGTKYJziBpGNeDdzGSwwXgsRLCCfPLhHJBKPv8dzqX3tGA8n8SA4tXhLdnGh-hws2gQgmCWEjF0RpzEdJA6jh6tGZyOSAa2GlTrLhuflBwjMB5-dc8JwRmI-ssOiXkO3fSRxnwWuWih24Co8-n8elsun4HxZVMqCzXepAiXBV9UBeUktV_PLclri_lTJEnDzoJRzfRyDigjb2-luODo9aX8DFseboggoCIMKDoyLPSVHnFXgs5EWV2aQ_DgRm_D6UPn2T1Gn7OAIe-T8aA7ypDCoR-wuTJdB8o7T0f2I8K-8FrXCy2Sgb8B5QPpAOcLdiBBqFxRdk8f2c67J-rSbm2WUPWK65pbLa8NGHHdIRKuiI87NmphWuKc39a_zcgEg4MnHSlDeephmStnLS8OayQObNdLQBYAmoeQeVpZRy9t9bcU"

 ```




 Response

```html 
{
  "fileName": "one-page.docx",
  "folder": "Output",
  "code": 200,
  "status": "OK"
}
 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Add Text Signature to Document ###





 C#




{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Text_Signature.cs >}}







 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Text_Signature.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Text_Signature.php >}}







 Ruby




{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Text_Signature.rb >}}







 Node




{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Text_Signature.js >}}







 Python




{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Text_Signature.py >}}









# Add Multiple Signatures to Document #

GroupDocs.Signature Cloud REST API supports to sign a document with multiple signatures. For example, you can add Text and Barcode signatures to a document at the same time. To put a list of signatures on the document (Cells, Images, PDF, Slides or Words) Signature API provides an object **[SignOptionsCollectionData]({{< ref "signature/developer-guide/data-structures/signsettings.md" >}}))** that can contain one or more signature options. Please, use signature options which appropriate for the current document format.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add a signature collection to a document](https://apireference.groupdocs.cloud/signature/#/Sign/CreateSignatures).

## cURL Example ##





 Request

```html 
curl --request POST \
--url http://api.groupdocs.cloud/v2/signature/01_pages.pdf/collection?folder#storage \
--header 'authorization: [Access Token]' \
--header 'content-type: application/json' \
--data '{ "items": [ { "barcodeTypeName": "Code39Standard", "borderVisiblity": true, "borderDashStyle": "Dash", "borderWeight": 12.0, "opacity": 0.8, "text": "123456789012", "left": 2, "top": 100, "width": 200, "height": 100, "locationMeasureType": "Pixels", "sizeMeasureType": "Pixels", "stretch": "None", "rotationAngle": 0, "horizontalAlignment": "Default", "verticalAlignment": "Default", "margin": { "all": 5, "left": 5, "top": 5, "right": 5, "bottom": 5 }, "marginMeasureType": "Pixels", "signAllPages": false, "font": { "fontFamily": "Times New Roman", "fontSize": 14.0, "bold": false, "italic": false, "underline": false }, "foreColor": { "Web": "DarkOrange" }, "borderColor": { "Web": "DarkOrange" }, "backgroundColor": { "Web": "BlueViolet" }, "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [  1 ] }, "OptionsType": "PdfSignBarcodeOptionsData" }, { "reason": "PdfDigitalReason", "contact": "PdfDigitalContact", "location": "PdfDigitalLocation", "visible": true, "password": "1234567890", "certificateGuid": "certificates\SherlockHolmes.pfx", "imageGuid": "images\signature_01.jpg", "left": 2, "top": 500, "width": 200, "height": 100, "locationMeasureType": "Pixels", "sizeMeasureType": "Pixels", "rotationAngle": 45, "horizontalAlignment": "Default", "verticalAlignment": "Default", "margin": { "all": 5, "left": 5, "top": 5, "right": 5, "bottom": 5 }, "marginMeasureType": "Pixels", "opacity": 0.9, "signAllPages": false, "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [  1 ] }, "OptionsType": "PdfSignDigitalOptionsData" } ] }'


 ```




 Response

```html 
{
  "fileName": "01_pages.pdf",
  "folder": "Output",
  "code": 200,
  "status": "OK"
}
 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Add Multiple Signatures to Document ###





 C#




{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Collection_Signature.cs >}}







 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Collection_Signature.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Collection_Signature.php >}}







 Ruby




{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Collection_Signature.rb >}}







 Node




{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Collection_Signature.js >}}







 Python




{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Collection_Signature.py >}}







 

 



 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Stamp_Signature.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Stamp_Signature.php >}}





