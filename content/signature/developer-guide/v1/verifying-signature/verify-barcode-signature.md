---
id: "verify-barcode-signature"
url: "signature/verify-barcode-signature"
title: "Verify Barcode Signature"
productName: "GroupDocs.Signature Cloud"
weight: 1
description: ""
keywords: ""
toc: True
---

{{< alert style="info" >}}
Note:  The features listed on this page are supported only in GroupDocs.Signature Cloud V1
{{< /alert >}}

GroupDocs.Signature Cloud REST API supports to verify a signed document. It provides methods to verify Barcode Signature in Documents Pages with different options for page number, text and search criteria by using [verification-options-objects]({{< ref "signature/developer-guide/v1/common-resources/verification-options-objects.md" >}}) data in request body.

## Verify Barcode Signature in a Document

You can Verify Barcode Signature in a Document using this API. It expects [Verification Options Object]({{< ref "signature/developer-guide/v1/common-resources/verification-options-objects.md" >}}) data in request body. It returns object which contains result of verification process. The field Result keeps flag if verification processed successfully.

### Resource

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to verify Barcode signature in a document](https://apireference.groupdocs.cloud/signature/#!/Verification/PostVerificationBarcode).

### cURL example

{{< tabs "example1">}} {{< tab "Linux/MacOS/Bash" >}}
```bash
# Verify barcode in a PDF document
curl -v "https://api.groupdocs.cloud/v1/signature/Signed_BarCode.pdf/barcode/verification?Folder#signed" \
  -X POST \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -H "Authorization: Bearer $JWT_TOKEN" \
  -d '{
        "BarcodeTypeName":"Code128",
        "Text":"1234567890",
        "VerifyAllPages":false,
        "DocumentPageNumber":1,
        "OptionsType":"PdfVerifyBarcodeOptionsData"
      }'
```
{{< /tab >}}

{{< tab "Windows PowerShell" >}}
```powershell
# Verify barcode in a PDF document
curl.exe -v "https://api.groupdocs.cloud/v1/signature/Signed_BarCode.pdf/barcode/verification?Folder#signed" `
  -X POST `
  -H "Content-Type: application/json" `
  -H "Accept: application/json" `
  -H "Authorization: Bearer $env:JWT_TOKEN" `
  -d '{ "BarcodeTypeName":"Code128","Text":"1234567890","VerifyAllPages":false,"DocumentPageNumber":1,"OptionsType":"PdfVerifyBarcodeOptionsData" }'
```
{{< /tab >}}

{{< tab "Windows CMD" >}}
```cmd
:: Verify barcode in a PDF document
curl -v "https://api.groupdocs.cloud/v1/signature/Signed_BarCode.pdf/barcode/verification?Folder#signed" ^
  -X POST ^
  -H "Content-Type: application/json" ^
  -H "Accept: application/json" ^
  -H "Authorization: Bearer %JWT_TOKEN%" ^
  -d "{\"BarcodeTypeName\":\"Code128\",\"Text\":\"1234567890\",\"VerifyAllPages\":false,\"DocumentPageNumber\":1,\"OptionsType\":\"PdfVerifyBarcodeOptionsData\"}"
```
{{< /tab >}} {{< tab "Response" >}}

```javascript
{
  "result": true,
  "fileName": "Signed_BarCode.pdf",
  "folder": "signed",
  "code": 200,
  "status": "OK"
}

```

{{< /tab >}} {{< /tabs >}}

### SDK examples

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](/signature/available-sdks).

{{< tabs "example2">}} {{< tab "C#" >}}

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Verify_Signature_Barcode.cs >}}

{{< /tab >}} {{< tab "PHP" >}}

{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_Barcode_Verify.php >}}

{{< /tab >}} {{< tab "Java" >}}

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Verify_Signature_Barcode.java >}}

{{< /tab >}} {{< tab "Python" >}}

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Verify_Signature_Barcode.py >}}

{{< /tab >}} {{< tab "Ruby" >}}

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Signature_Signature_Barcode.rb >}}

{{< /tab >}} {{< /tabs >}}

## Verify Barcode Signature in a Document at Provided URL

GroupDocs.Signature Cloud REST API supports to verify Barcode Signature for document at provided URL with [verification-options-objects]({{< ref "signature/developer-guide/v1/common-resources/verification-options-objects.md" >}}). The API retrieves file from specified URL and tries to detect file type when fileName parameter is not specified. It expects [verification-options-objects]({{< ref "signature/developer-guide/v1/common-resources/verification-options-objects.md" >}})  data in request body. Based on passed Verification Options settings proceeds with Document verification and returns object which contains result of verification process. The field Result keeps flag if verification processed successfully.

### Resource

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to verify Barcode signature in a document at provided URL](https://apireference.groupdocs.cloud/signature/#!/Verification/PostVerificationBarcodeFromUrl).

### cURL example

{{< tabs "example3">}} {{< tab "Linux/MacOS/Bash" >}}
```bash
# Verify barcode in a document from URL
curl -v "https://api-qa.groupdocs.cloud/v1/signature/barcode/verification?url#https%3A%2F%2Fwww.dropbox.com%2Fs%2Fbzx1xm68zd0c910%2FPieChart.docx&#x26;signature#ZTbpiS7dNO0sxXFhnkl62asm5T0" \
  -X POST \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -H "Authorization: Bearer $JWT_TOKEN" \
  -d '{
        "BarcodeTypeName":"Code128",
        "MatchType":"Exact",
        "DocumentPageNumber":1,
        "Text":"John Smith",
        "VerifyAllPages":true,
        "OptionsType":"WordsVerifyBarcodeOptionsData"
      }'
```
{{< /tab >}}

{{< tab "Windows PowerShell" >}}
```powershell
# Verify barcode in a document from URL
curl.exe -v "https://api-qa.groupdocs.cloud/v1/signature/barcode/verification?url#https%3A%2F%2Fwww.dropbox.com%2Fs%2Fbzx1xm68zd0c910%2FPieChart.docx&#x26;signature#ZTbpiS7dNO0sxXFhnkl62asm5T0" `
  -X POST `
  -H "Content-Type: application/json" `
  -H "Accept: application/json" `
  -H "Authorization: Bearer $env:JWT_TOKEN" `
  -d '{ "BarcodeTypeName":"Code128","MatchType":"Exact","DocumentPageNumber":1,"Text":"John Smith","VerifyAllPages":true,"OptionsType":"WordsVerifyBarcodeOptionsData" }'
```
{{< /tab >}}

{{< tab "Windows CMD" >}}
```cmd
:: Verify barcode in a document from URL
curl -v "https://api-qa.groupdocs.cloud/v1/signature/barcode/verification?url#https%3A%2F%2Fwww.dropbox.com%2Fs%2Fbzx1xm68zd0c910%2FPieChart.docx&#x26;signature#ZTbpiS7dNO0sxXFhnkl62asm5T0" ^
  -X POST ^
  -H "Content-Type: application/json" ^
  -H "Accept: application/json" ^
  -H "Authorization: Bearer %JWT_TOKEN%" ^
  -d "{\"BarcodeTypeName\":\"Code128\",\"MatchType\":\"Exact\",\"DocumentPageNumber\":1,\"Text\":\"John Smith\",\"VerifyAllPages\":true,\"OptionsType\":\"WordsVerifyBarcodeOptionsData\"}"
```
{{< /tab >}} {{< tab "Response" >}}

```javascript
{
  "result": false,
  "fileName": "https://www.dropbox.com/s/bzx1xm68zd0c910/PieChart.docx",
  "folder": "",
  "code": 200,
  "status": "OK"
}
```

{{< /tab >}} {{< /tabs >}}

### SDK examples

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](/signature/available-sdks).

{{< tabs "example4">}} {{< tab "C#" >}}

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Verify_Signature_Barcode_URL.cs >}}

{{< /tab >}} {{< tab "PHP" >}}

{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_Barcode_Verify_URL.php >}}

{{< /tab >}} {{< tab "Java" >}}

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Verify_Signature_Barcode_URL.java >}}

{{< /tab >}} {{< tab "Python" >}}

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Verify_Signature_Barcode_URL.py >}}

{{< /tab >}} {{< tab "Ruby" >}}

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Signature_Signature_Barcode_URL.rb >}}

{{< /tab >}} {{< /tabs >}}

