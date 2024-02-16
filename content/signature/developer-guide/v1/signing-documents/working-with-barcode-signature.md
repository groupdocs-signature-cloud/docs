---
id: "working-with-barcode-signature"
url: "signature/working-with-barcode-signature"
title: "Working with Barcode Signature"
productName: "GroupDocs.Signature Cloud"
weight: 1
description: ""
keywords: ""
toc: True
---

{{< alert style="info" >}}
Note:  The features listed on this page are supported only in GroupDocs.Signature Cloud V1
{{< /alert >}}

GroupDocs.Signature Cloud REST API supports to sign a document with Barcode. It provides methods to create Barcode Signature in Document Pages with different options of Barcode type, location, alignment, font, margins and appearances by using [signature-options-objects]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}) object data in request body.

## Add Barcode Signature to Document

You can create Barcode Signature on Document provided by fileName and document folder (if required) using following API. It expects [Signature Options Object]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}) data in request body.

It returns an object which contains document name, folder location and signing result.

### Resource

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add Barcode signature to a document](https://apireference.groupdocs.cloud/signature/#!/Signing/PostBarcode).

### cURL example

{{< tabs "example1">}} {{< tab "Request" >}}

```javascript
curl -v "https://api.groupdocs.cloud/v1/signature/one-page.docx/barcode" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d "{"BarcodeTypeName": "Code128","BorderVisiblity" : true,"BorderDashStyle" : "DashDotDot","BorderWeight" : 1,"Opacity" : 0.5,"Margin": {"All": 0,"Left": 0,"Top": 0,"Right": 0,"Bottom": 0},"SheetNumber": 1,"RowNumber": 11,"ColumnNumber": 22,"BorderVisiblity": true,"BorderDashStyle": 5,"BorderTransparency": 0.0,"BorderWeight": 1.0,"BackgroundTransparency": 0.1,"SignatureImplementation": "TextStamp","Text": "John Smith","Width": 100,"Height": 100,"LocationMeasureType": "Pixels","SizeMeasureType": "Pixels","RotationAngle": 0,"HorizontalAlignment": "Right","VerticalAlignment": "Center","MarginMeasureType": "Pixels","SignAllPages": false,"Font": {"FontFamily": "Times New Roman","FontSize": 14.0,"Bold": false,"Italic": false,"Underline": false},"ForeColor": {"Web": "Black"},"BorderColor": {"Web": "Black"},"BackgroundColor": {"Web": "OrangeRed"},"OptionsType": "WordsSignBarcodeOptionsData"}" -H "authorization: Bearer _0zqJ6w3enMdpEw5C6ZKm3lgYvHell1lHdx3vztekvBpCbZGqMvMplrKNrsVXih9Xe6738GSej2hb0BnwKVVz-ANEOnW0bGqjeiJcEySo2Y9-9VZ1K_rs_p4zZcsMoGNuDkL9G4rowGX9Wd1frChwRXzsJCpJUs9G5fGK-0kochaFTVdMgoOHU8JjUOQ5wiu-_ZQSbR0bMKRamxEyc_P_gv9NU7LTJQTCrP1SIJwem1WTX7GaTr8JRUYE0zsXH2vHUkJ1rNh-1RPblqE6wwrfxkklTCGxAWTxvoaSG-Ax-h2Zl9nZkBCAjS48zzz2kqIWS-K5WUmGPP9hAWQL00_deMB0Qi7xqvf2MWoJ831mFnyse-ZQ80fAqPyFBdYpS-xVFC0Uuc8rVHehydCxD0_oIJWkCU_GuDJpNMv6q4IpM-1RzFn"

```

{{< /tab >}} {{< tab "Response" >}}

```javascript
{
  "fileName": "one-page.docx",
  "folder": "Output",
  "code": 200,
  "status": "OK"
}
```

{{< /tab >}} {{< /tabs >}}

### SDK examples

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](/signature/available-sdks).

{{< tabs "example2">}} {{< tab "C#" >}}

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Signature_Barcode.cs >}}

{{< /tab >}} {{< tab "PHP" >}}

{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_Barcode.php >}}

{{< /tab >}} {{< tab "Java" >}}

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Signature_Barcode.java >}}

{{< /tab >}} {{< tab "Python" >}}

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Signature_Barcode.py >}}

{{< /tab >}} {{< tab "Ruby" >}}

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Signature_Barcode.rb >}}

{{< /tab >}} {{< /tabs >}}

## Add Barcode Signature to Document at Provided URL

You can creates Barcode Signature for document at provided URL with [signature-options-objects]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}). It retrieves file from specified URL and tries to detect file type when fileName parameter is not specified. It saves retrieved file in storage, by using fileName and folder parameters to specify desired file name and folder to save file. When file with specified name already exists in storage new unique file name will be used for file. It expects [Signature Options Object]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}) data in request body and returns object which contains document name and folder location.

### Resource

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add Barcode signature to a document at provided URL](https://apireference.groupdocs.cloud/signature/#!/Signing/PostBarcodeFromUrl).

### cURL example

{{< tabs "example3">}} {{< tab "Request" >}}

```javascript

curl -X POST "https:~/~/api.groupdocs.cloud/v2.0/signature/create" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]" -H  "Content-Type: application/json" -d "{  \"FileInfo\": {    \"FilePath\": \"files01.docx\",  },   \"SaveOptions\": {    \"OverwriteExisting\": \"true\",    \"OutputFilePath\": \"file02.docx\",    \"SaveFormat\": \"docx\"  },  \"SignOptions\":   [    {      \"DocumentType\": \"WordProcessing\",      \"SignatureType\": \"Barcode\",        \"Page\": 1,      \"Text\": \"John Smith\",      \"BarcodeType\": \"Code128\",      \"Left\": 2,      \"Top\": 2    },    {      \"DocumentType\": \"WordProcessing\",      \"SignatureType\": \"Image\",        \"Page\": 1,      \"ImageGuid\": \"image1.jpg\",      \"Left\": 200,      \"Top\": 200,      \"Opacity\": 0.5    }    ] }"

```

{{< /tab >}} {{< tab "Response" >}}

```javascript
{
  "fileName": "one-page.docx",
  "folder": "Output",
  "Code": 200,
  "Status" : "OK"
}
```

{{< /tab >}} {{< /tabs >}}

### SDK examples

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](/signature/available-sdks).


{{< tabs "example4">}} {{< tab "C#" >}}

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Signature_Barcode_From_URL.cs >}}

{{< /tab >}} {{< tab "PHP" >}}

{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_Barcode_URL.php >}}

{{< /tab >}} {{< tab "Java" >}}

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Signature_Barcode_From_URL.java >}}

{{< /tab >}} {{< tab "Python" >}}

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Signature_Barcode_From_URL.py >}}

{{< /tab >}} {{< tab "Ruby" >}}

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Barcode_From_URL.rb >}}

{{< /tab >}} {{< /tabs >}}
