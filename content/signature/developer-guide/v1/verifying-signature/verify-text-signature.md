---
id: "verify-text-signature"
url: "signature/verify-text-signature"
title: "Verify Text Signature"
productName: "GroupDocs.Signature Cloud"
weight: 1
description: ""
keywords: ""
toc: True
---

{{< alert style="info" >}}
Note:  The features listed on this page are supported only in GroupDocs.Signature Cloud V1
{{< /alert >}}

GroupDocs.Signature Cloud REST API supports to verify a signed document. It provides methods to verify Text Signature in Documents Pages with different options for page number, text and search criteria by using `Verification Options` Objects data in request body.

## Verify Text Signature in a Document

You can verify Text Signature in a Document using this API. It expects `Verification Options` Objects data in request body. It returns object which contains result of verification process. The field Result keeps flag if verification processed successfully.

### Resource

The following GroupDocs.Signature Cloud REST API resource has been used [to verify Text signature in a document](https://apireference.groupdocs.cloud/signature/#!/Verification/PostVerificationText) example.

### cURL example

{{< tabs "example1">}} {{< tab "Linux/MacOS/Bash" >}}
```bash
curl -v "https://api.groupdocs.cloud/v1/signature/Signed_Text.pdf/text/verification?Folder#signed" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"DocumentPageNumber":1,"Text":"1234567890","VerifyAllPages":true,"OptionsType":"PdfVerifyTextOptionsData"}' \
-H "authorization: Bearer $JWT_TOKEN"
```
{{< /tab >}}

{{< tab "Windows PowerShell" >}}
```powershell
curl.exe -v "https://api.groupdocs.cloud/v1/signature/Signed_Text.pdf/text/verification?Folder#signed" `
-X POST `
-H "Content-Type: application/json" `
-H "Accept: application/json" `
-d "`{
    'DocumentPageNumber':1,
    'Text':'1234567890',
    'VerifyAllPages':$true,
    'OptionsType':'PdfVerifyTextOptionsData'
}`" `
-H "authorization: Bearer $env:JWT_TOKEN"
```
{{< /tab >}}

{{< tab "Windows CMD" >}}
```cmd
curl -v "https://api.groupdocs.cloud/v1/signature/Signed_Text.pdf/text/verification?Folder#signed" ^
-X POST ^
-H "Content-Type: application/json" ^
-H "Accept: application/json" ^
-d "{\"DocumentPageNumber\":1,\"Text\":\"1234567890\",\"VerifyAllPages\":true,\"OptionsType\":\"PdfVerifyTextOptionsData\"}" ^
-H "authorization: Bearer %JWT_TOKEN%"
```
{{< /tab >}} {{< tab "Response" >}}

```javascript
{
  "result": true,
  "fileName": "Signed_Text.pdf",
  "folder": "signed",
  "code": 200,
  "status": "OK"
}
```

{{< /tab >}} {{< /tabs >}}

### SDK examples

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](/signature/available-sdks).

{{< tabs "example2">}} {{< tab "C#" >}}

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Verify_Signature_Text.cs >}}

{{< /tab >}} {{< tab "PHP" >}}

{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_Text_Verify.php >}}

{{< /tab >}} {{< tab "Java" >}}

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Verify_Signature_Text.java >}}

{{< /tab >}} {{< tab "Python" >}}

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Verify_Signature_Text.py >}}

{{< /tab >}} {{< tab "Ruby" >}}

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Signature_Signature_Text.rb >}}

{{< /tab >}} {{< /tabs >}}

## Verify Text Signature in a Document at Provided URL

GroupDocs.Signature Cloud REST API supports to verify Text Signature for document at provided URL with `Verification Options` Objects. The API retrieves file from specified URL and tries to detect file type when fileName parameter is not specified. It expects `Verification Options` Objects  data in request body. Based on passed Verification Options settings proceeds with Document verification and returns object which contains result of verification process. The field Result keeps flag if verification processed successfully.

### Resource

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to verify Text signature in a document at provided URL](https://apireference.groupdocs.cloud/signature/#!/Verification/PostVerificationTextFromUrl).

### cURL example

{{< tabs "example3">}} {{< tab "Linux/MacOS/Bash" >}}
```bash
curl -v "https://api-qa.groupdocs.cloud/v1/signature/text/verification?url#https%3A%2F%2Fwww.dropbox.com%2Fs%2Fbzx1xm68zd0c910%2FPieChart.docx" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d '{"DocumentPageNumber":1,"Text":"coca cola","VerifyAllPages":true,"OptionsType":"WordsVerifyTextOptionsData"}' \
-H "authorization: Bearer $JWT_TOKEN"
```
{{< /tab >}}

{{< tab "Windows PowerShell" >}}
```powershell
curl.exe -v "https://api-qa.groupdocs.cloud/v1/signature/text/verification?url#https%3A%2F%2Fwww.dropbox.com%2Fs%2Fbzx1xm68zd0c910%2FPieChart.docx" `
-X POST `
-H "Content-Type: application/json" `
-H "Accept: application/json" `
-d "`{
    'DocumentPageNumber':1,
    'Text':'coca cola',
    'VerifyAllPages':$true,
    'OptionsType':'WordsVerifyTextOptionsData'
}`" `
-H "authorization: Bearer $env:JWT_TOKEN"
```
{{< /tab >}}

{{< tab "Windows CMD" >}}
```cmd
curl -v "https://api-qa.groupdocs.cloud/v1/signature/text/verification?url#https%3A%2F%2Fwww.dropbox.com%2Fs%2Fbzx1xm68zd0c910%2FPieChart.docx" ^
-X POST ^
-H "Content-Type: application/json" ^
-H "Accept: application/json" ^
-d "{\"DocumentPageNumber\":1,\"Text\":\"coca cola\",\"VerifyAllPages\":true,\"OptionsType\":\"WordsVerifyTextOptionsData\"}" ^
-H "authorization: Bearer %JWT_TOKEN%"
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

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Verify_Signature_Text_URL.cs >}}

{{< /tab >}} {{< tab "PHP" >}}

{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_Text_Verify_URL.php >}}

{{< /tab >}} {{< tab "Java" >}}

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Verify_Signature_Text_URL.java >}}

{{< /tab >}} {{< tab "Python" >}}

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Verify_Signature_Text_URL.py >}}

{{< /tab >}} {{< tab "Ruby" >}}

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Signature_Signature_Text_URL.rb >}}

{{< /tab >}} {{< /tabs >}}

