---
id: "document-information"
url: "signature/document-information"
title: "Document Information"
productName: "GroupDocs.Signature Cloud"
weight: 4
description: ""
keywords: ""
toc: True
---

{{< alert style="info" >}}
Note:  The features listed in this page are supported only in GroupDocs.Signature Cloud V1
{{< /alert >}}

## Get Document Information

This API retrieves document information. It returns an object that contains information about file format, document pages and file size.

### Resource

The following GroupDocs.Signature Cloud REST API resource has been used to get [document information](https://apireference.groupdocs.cloud/signature/#!/File_Info/GetDocumentInfo).

### cURL example

{{< tabs "example1">}} {{< tab "Linux/MacOS/Bash" >}}

```bash
curl -v "https://api.groupdocs.cloud/v1/signature/document.docx/document/info" \
  -X GET \
  -H "Content-Type: application/json" \
  -H "authorization: Bearer $JWT_TOKEN"
```

{{< /tab >}}

{{< tab "Windows PowerShell" >}}

```powershell
curl.exe -v "https://api.groupdocs.cloud/v1/signature/document.docx/document/info" `
  -X GET `
  -H "Content-Type: application/json" `
  -H "authorization: Bearer $env:JWT_TOKEN"
```

{{< /tab >}}

{{< tab "Windows CMD" >}}

```cmd
curl -v "https://api.groupdocs.cloud/v1/signature/document.docx/document/info" ^ 
  -X GET ^ 
  -H "Content-Type: application/json" ^ 
  -H "authorization: Bearer %JWT_TOKEN%"
```

{{< /tab >}} {{< tab "Response" >}}

```javascript
{
  "fileName": "document.docx",
  "extension": ".docx",
  "fileFormat": "Microsoft Words",
  "size": 324608,
  "dateModified": "2017-04-03T12:57:58.9646989Z",
  "pages": {
    "totalCount": 1,
    "entries": [
      {
        "number": 1,
        "name": null,
        "width": 816,
        "height": 1056,
        "angle": 0,
        "visible": true,
        "rows": null
      }
    ]
  }
}
```

{{< /tab >}} {{< /tabs >}}

### SDK examples

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](/signature/available-sdks).

{{< tabs "example2">}} {{< tab "C#" >}}

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_DocumentInfo_File.cs >}}

{{< /tab >}} {{< tab "Java" >}}

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_DocumentInfo_File.java >}}

{{< /tab >}} {{< tab "Python" >}}

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_DocumentInfo_File.py >}}

{{< /tab >}} {{< tab "Ruby" >}}

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_DocumentInfo_File.rb >}}

{{< /tab >}} {{< /tabs >}}

## Get Document Information from provided URL

This API retrieves document information for document at provided URL. It retrieves file from specified URL and tries to detect file type when fileName parameter is not specified. It saves retrieved file in storage, uses fileName and folder parameters to specify desired file name and folder to save file. When file with specified name already exists in storage new unique file name will be used. It returns an object that contains information about file format and file size. It also includes information about document pages and attachments.

### Resource

The following GroupDocs.Signature Cloud REST API resource has been used to get [document information from provided URL](https://apireference.groupdocs.cloud/signature/#!/File_Info/GetDocumentInfoFromUrl).

### cURL example

{{< tabs "example3">}} {{< tab "Linux/MacOS/Bash" >}}

```bash
curl -v "https://api.groupdocs.cloud/v1/signature/document/info?url#https%3a%2f%2fwww.dropbox.com%2fs%2fumokluz338w4ng7%2fone-page.docx%3fdl%3d1" \
  -X GET \
  -H "Content-Type: application/json" \
  -H "authorization: Bearer $JWT_TOKEN"
```

{{< /tab >}}

{{< tab "Windows PowerShell" >}}

```powershell
curl.exe -v "https://api.groupdocs.cloud/v1/signature/document/info?url#https%3a%2f%2fwww.dropbox.com%2fs%2fumokluz338w4ng7%2fone-page.docx%3fdl%3d1" `
  -X GET `
  -H "Content-Type: application/json" `
  -H "authorization: Bearer $env:JWT_TOKEN"
```

{{< /tab >}}

{{< tab "Windows CMD" >}}

```cmd
curl -v "https://api.groupdocs.cloud/v1/signature/document/info?url#https%3a%2f%2fwww.dropbox.com%2fs%2fumokluz338w4ng7%2fone-page.docx%3fdl%3d1" ^ 
  -X GET ^ 
  -H "Content-Type: application/json" ^ 
  -H "authorization: Bearer %JWT_TOKEN%"
```

{{< /tab >}} {{< tab "Response" >}}

```javascript
{
  "fileName": "document.docx",
  "extension": ".docx",
  "fileFormat": "Microsoft Words",
  "size": 324608,
  "dateModified": "2017-04-03T12:57:58.9646989Z",
  "pages": {
    "totalCount": 1,
    "entries": [
      {
        "number": 1,
        "name": null,
        "width": 816,
        "height": 1056,
        "angle": 0,
        "visible": true,
        "rows": null
      }
    ]
  }
}
```

{{< /tab >}} {{< /tabs >}}

### SDK examples

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](/signature/available-sdks).

{{< tabs "example4">}} {{< tab "C#" >}}

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_DocumentInfo_URL.cs >}}

{{< /tab >}} {{< tab "Java" >}}

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_DocumentInfo_URL.java >}}

{{< /tab >}} {{< tab "Python" >}}

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_DocumentInfo_URL.py >}}

{{< /tab >}} {{< tab "Ruby" >}}

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_DocumentInfo_URL.rb >}}

{{< /tab >}} {{< /tabs >}}
