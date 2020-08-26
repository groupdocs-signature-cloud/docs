---
id: "get-supported-file-formats"
url: "signature/get-supported-file-formats"
title: "Get Supported File Formats"
productName: "GroupDocs.Signature Cloud"
weight: 1
description: ""
keywords: ""
---

# Introduction #

GroupDocs.Signature Cloud is a REST API to create, verify and search different type of Signatures objects in all common business formats, including PDF, Microsoft Word, Excel, PowerPoint, epub and many other files. To get list of supported file formats, you can use the following API.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the [Supported File Formats](https://apireference.groupdocs.cloud/signature/#!/Helper/GetSupportedFormats) example.

## cURL Example ##

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}} {{< tab tabNum="1" >}}

```javascript
curl -X GET "https://api.groupdocs.cloud/v2.0/signature/formats" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
```

{{< /tab >}} {{< tab tabNum="2" >}}

```javascript
{
  "formats": [
    {
      "extension": ".pdf",
      "fileFormat": "Portable Document Format"
    },
    {
      "extension": ".doc",
      "fileFormat": "Microsoft Word"
    },
    {
      "extension": ".docx",
      "fileFormat": "Microsoft Word"
    },
    {
      "extension": ".docm",
      "fileFormat": "Microsoft Word"
    },
    {
      "extension": ".dot",
      "fileFormat": "Microsoft Word"
    },
    {
      "extension": ".dotx",
      "fileFormat": "Microsoft Word"
    },
    {
      "extension": ".dotm",
      "fileFormat": "Microsoft Word"
    },
    {
      "extension": ".xls",
      "fileFormat": "Microsoft Excel"
    },
    {
      "extension": ".xlsx",
      "fileFormat": "Microsoft Excel"
    },
    {
      "extension": ".xlsm",
      "fileFormat": "Microsoft Excel"
    },
    {
      "extension": ".xlsb",
      "fileFormat": "Microsoft Excel"
    },
    {
      "extension": ".ppt",
      "fileFormat": "Microsoft PowerPoint"
    },
    {
      "extension": ".pptx",
      "fileFormat": "Microsoft PowerPoint"
    },
    {
      "extension": ".pps",
      "fileFormat": "Microsoft PowerPoint"
    },
    {
      "extension": ".ppsx",
      "fileFormat": "Microsoft PowerPoint"
    },
    {
      "extension": ".odt",
      "fileFormat": "OpenDocument Formats"
    },
    {
      "extension": ".ott",
      "fileFormat": "OpenDocument Formats"
    },
    {
      "extension": ".ods",
      "fileFormat": "OpenDocument Formats"
    },
    {
      "extension": ".odp",
      "fileFormat": "OpenDocument Formats"
    },
    {
      "extension": ".otp",
      "fileFormat": "OpenDocument Formats"
    },
    {
      "extension": ".ots",
      "fileFormat": "OpenDocument Formats"
    },
    {
      "extension": ".rtf",
      "fileFormat": "Rich Text Format"
    },
    {
      "extension": ".txt",
      "fileFormat": "Plain Text File"
    },
    {
      "extension": ".csv",
      "fileFormat": "Comma-Separated Values"
    },
    {
      "extension": ".html",
      "fileFormat": "HyperText Markup Language"
    },
    {
      "extension": ".mht",
      "fileFormat": "HyperText Markup Language"
    },
    {
      "extension": ".xml",
      "fileFormat": "Extensible Markup Language"
    },
    {
      "extension": ".xps",
      "fileFormat": "XML Paper Specification"
    },
    {
      "extension": ".bmp",
      "fileFormat": "Image files"
    },
    {
      "extension": ".gif",
      "fileFormat": "Image files"
    },
    {
      "extension": ".jpg",
      "fileFormat": "Image files"
    },
    {
      "extension": ".jpeg",
      "fileFormat": "Image files"
    },
    {
      "extension": ".png",
      "fileFormat": "Image files"
    },
    {
      "extension": ".tiff",
      "fileFormat": "Image files"
    },
    {
      "extension": ".djvu",
      "fileFormat": "Image files"
    },
    {
      "extension": ".webp",
      "fileFormat": "Image files"
    },
    {
      "extension": ".epub",
      "fileFormat": "Electronic publication"
    }
  ]
}
{{< /tab >}} {{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Get List of Supported File Formats ###

C#

{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Get_Supported_Formats.cs >}}

Java

{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Get_Supported_Formats.java >}}

PHP

{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Get_Supported_Formats.php >}}

Ruby

{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Get_Supported_Formats.rb >}}

Node

{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Get_All_Supported_Formats.js >}}

Python

{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Get_All_Supported_Formats.py >}}
