---
id: "working-with-digital-signature"
url: "signature/working-with-digital-signature"
title: "Working with Digital Signature"
productName: "GroupDocs.Signature Cloud"
weight: 2
description: ""
keywords: ""
toc: True
---

{{< alert style="info" >}}
Note:  The features listed on this page are supported only in GroupDocs.Signature Cloud V1
{{< /alert >}}

GroupDocs.Signature Cloud REST API supports to add Digital Signature to a document. It provides methods to create Digital Signature in Document Pages with different options of Certificate type, location, alignment, font, margins and appearances by using [Signature Options Object]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}) data in request body.

## Add Digital Signature to Document

You can create Digital Signature on Document provided by fileName and document folder (if required) using following API. It expects [Signature Options Object]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}) data in request body.

It returns an object which contains document name, folder location and process result.

## Resource

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add Digital signature to a document](https://apireference.groupdocs.cloud/signature/#!/Signing/PostDigital).

## cURL example

{{< tabs "example1">}} {{< tab "Linux/MacOS/Bash" >}}
```bash
curl -v "https://api.groupdocs.cloud/v1/signature/01_pages.pdf/digital" \
  -X POST \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -d '{"Visible":true,"Password":"password","CertificateGuid":"temp.pfx","ImageGuid":"signature.jpg","Left":10,"Top":10,"Width":40,"Height":10,"LocationMeasureType":"Millimeters","SizeMeasureType":"Millimeters","RotationAngle":0,"HorizontalAlignment":"Right","VerticalAlignment":"Bottom","Margin":{"All":10,"Left":10,"Top":10,"Right":10,"Bottom":10},"MarginMeasureType":"Millimeters","Opacity":0.5,"SignAllPages":true,"DocumentPageNumber":1,"OptionsType":"PdfSignDigitalOptionsData"}' \
  -H "authorization: Bearer $JWT_TOKEN"
```
{{< /tab >}}

{{< tab "Windows PowerShell" >}}
```powershell
curl.exe -v "https://api.groupdocs.cloud/v1/signature/01_pages.pdf/digital" `
  -X POST `
  -H "Content-Type: application/json" `
  -H "Accept: application/json" `
  -d @'
{
    "Visible": true,
    "Password": "password",
    "CertificateGuid": "temp.pfx",
    "ImageGuid": "signature.jpg",
    "Left": 10,
    "Top": 10,
    "Width": 40,
    "Height": 10,
    "LocationMeasureType": "Millimeters",
    "SizeMeasureType": "Millimeters",
    "RotationAngle": 0,
    "HorizontalAlignment": "Right",
    "VerticalAlignment": "Bottom",
    "Margin": {
        "All": 10,
        "Left": 10,
        "Top": 10,
        "Right": 10,
        "Bottom": 10
    },
    "MarginMeasureType": "Millimeters",
    "Opacity": 0.5,
    "SignAllPages": true,
    "DocumentPageNumber": 1,
    "OptionsType": "PdfSignDigitalOptionsData"
}
'@ `
  -H "authorization: Bearer $env:JWT_TOKEN"
```
{{< /tab >}}

{{< tab "Windows CMD" >}}
```cmd
curl -v "https://api.groupdocs.cloud/v1/signature/01_pages.pdf/digital" ^
  -X POST ^
  -H "Content-Type: application/json" ^
  -H "Accept: application/json" ^
  -d "{\"Visible\":true,\"Password\":\"password\",\"CertificateGuid\":\"temp.pfx\",\"ImageGuid\":\"signature.jpg\",\"Left\":10,\"Top\":10,\"Width\":40,\"Height\":10,\"LocationMeasureType\":\"Millimeters\",\"SizeMeasureType\":\"Millimeters\",\"RotationAngle\":0,\"HorizontalAlignment\":\"Right\",\"VerticalAlignment\":\"Bottom\",\"Margin\":{\"All\":10,\"Left\":10,\"Top\":10,\"Right\":10,\"Bottom\":10},\"MarginMeasureType\":\"Millimeters\",\"Opacity\":0.5,\"SignAllPages\":true,\"DocumentPageNumber\":1,\"OptionsType\":\"PdfSignDigitalOptionsData\"}" ^
  -H "authorization: Bearer %JWT_TOKEN%"
```
{{< /tab >}} {{< tab "Response" >}}

```javascript
{
  "fileName": "one-page.pdf",
  "folder": "Output",
  "code": 200,
  "status": "OK"
}
```

{{< /tab >}} {{< /tabs >}}

### SDK examples

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](/signature/available-sdks).

{{< tabs "example2">}} {{< tab "C#" >}}

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Signature_Digital.cs >}}

{{< /tab >}} {{< tab "PHP" >}}

{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_Digital.php >}}

{{< /tab >}} {{< tab "Java" >}}

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Signature_Digital.java >}}

{{< /tab >}} {{< tab "Python" >}}

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Signature_Digital.py >}}

{{< /tab >}} {{< tab "Ruby" >}}

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Signature_Digital.rb >}}

{{< /tab >}} {{< /tabs >}}

## Add Digital Signature to Document at Provided URL

You can creates Digital Signature for document at provided URL with [signature-options-objects]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}). It retrieves file from specified URL and tries to detect file type when fileName parameter is not specified. It saves retrieved file in storage, by using fileName and folder parameters to specify desired file name and folder to save file. When file with specified name already exists in storage new unique file name will be used for file. It expects [Signature Options Object]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}) data in request body and returns object which contains document name and folder location.

## Resource

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add Digital signature to a document at provided URL](https://apireference.groupdocs.cloud/signature/#!/Signing/PostDigitalFromUrl).

## cURL example

{{< tabs "example3">}} {{< tab "Linux/MacOS/Bash" >}}
```bash
curl -v "https://api.groupdocs.cloud/v1/signature/digital?url#https%3a%2f%2fwww.dropbox.com%2fs%2fumokluz338w4ng7%2fone-page.docx%3fdl%3d1" \
  -X POST \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -d '{"Margin":{"All":10,"Left":10,"Top":10,"Right":10,"Bottom":10},"DocumentPageNumber":1,"SheetNumber":1,"RowNumber":1,"ColumnNumber":2,"Password":"password","CertificateGuid":"temp.pfx","ImageGuid":"signature.jpg","Left":1,"Top":1,"Width":40,"Height":40,"LocationMeasureType":"Pixels","SizeMeasureType":"Millimeters","RotationAngle":0,"HorizontalAlignment":"Left","VerticalAlignment":"Bottom","MarginMeasureType":"Pixels","Opacity":0.5,"SignAllPages":true,"OptionsType":"WordsSignDigitalOptionsData"}' \
  -H "authorization: Bearer $JWT_TOKEN"
```
{{< /tab >}}

{{< tab "Windows PowerShell" >}}
```powershell
curl.exe -v "https://api.groupdocs.cloud/v1/signature/digital?url#https%3a%2f%2fwww.dropbox.com%2fs%2fumokluz338w4ng7%2fone-page.docx%3fdl%3d1" `
  -X POST `
  -H "Content-Type: application/json" `
  -H "Accept: application/json" `
  -d @'
{
    "Margin": {
        "All": 10,
        "Left": 10,
        "Top": 10,
        "Right": 10,
        "Bottom": 10
    },
    "DocumentPageNumber": 1,
    "SheetNumber": 1,
    "RowNumber": 1,
    "ColumnNumber": 2,
    "Password": "password",
    "CertificateGuid": "temp.pfx",
    "ImageGuid": "signature.jpg",
    "Left": 1,
    "Top": 1,
    "Width": 40,
    "Height": 40,
    "LocationMeasureType": "Pixels",
    "SizeMeasureType": "Millimeters",
    "RotationAngle": 0,
    "HorizontalAlignment": "Left",
    "VerticalAlignment": "Bottom",
    "MarginMeasureType": "Pixels",
    "Opacity": 0.5,
    "SignAllPages": true,
    "OptionsType": "WordsSignDigitalOptionsData"
}
'@ `
  -H "authorization: Bearer $env:JWT_TOKEN"
```
{{< /tab >}}

{{< tab "Windows CMD" >}}
```cmd
curl -v "https://api.groupdocs.cloud/v1/signature/digital?url#https%3a%2f%2fwww.dropbox.com%2fs%2fumokluz338w4ng7%2fone-page.docx%3fdl%3d1" ^
  -X POST ^
  -H "Content-Type: application/json" ^
  -H "Accept: application/json" ^
  -d "{\"Margin\":{\"All\":10,\"Left\":10,\"Top\":10,\"Right\":10,\"Bottom\":10},\"DocumentPageNumber\":1,\"SheetNumber\":1,\"RowNumber\":1,\"ColumnNumber\":2,\"Password\":\"password\",\"CertificateGuid\":\"temp.pfx\",\"ImageGuid\":\"signature.jpg\",\"Left\":1,\"Top\":1,\"Width\":40,\"Height\":40,\"LocationMeasureType\":\"Pixels\",\"SizeMeasureType\":\"Millimeters\",\"RotationAngle\":0,\"HorizontalAlignment\":\"Left\",\"VerticalAlignment\":\"Bottom\",\"MarginMeasureType\":\"Pixels\",\"Opacity\":0.5,\"SignAllPages\":true,\"OptionsType\":\"WordsSignDigitalOptionsData\"}" ^
  -H "authorization: Bearer %JWT_TOKEN%"
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

## SDK examples

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](/signature/available-sdks).

{{< tabs "example4">}} {{< tab "C#" >}}

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Signature_Digital_URL.cs >}}

{{< /tab >}} {{< tab "PHP" >}}

{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_Digital_URL.php >}}

{{< /tab >}} {{< tab "Java" >}}

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Signature_Digital_URL.java >}}

{{< /tab >}} {{< tab "Python" >}}

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Signature_Digital_URL.py >}}

{{< /tab >}} {{< tab "Ruby" >}}

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Signature_Digital_URL.rb >}}

{{< /tab >}} {{< /tabs >}}

