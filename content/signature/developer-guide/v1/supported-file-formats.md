---
id: "supported-file-formats"
url: "signature/supported-file-formats"
title: "Supported File Formats"
productName: "GroupDocs.Signature Cloud"
weight: 3
description: ""
keywords: ""
---

{{< alert style="info" >}}
Note:  The features listed in this page are supported only in GroupDocs.Signature Cloud V1
{{< /alert >}}







# Introduction #

GroupDocs.Signature Cloud is a REST API to create, verify and search different type of Signatures objects in all common business formats, including PDF, Microsoft Word, Excel, PowerPoint, epub and many other files. To get list of supported file formats, you can use the following API. 

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the [Supported File Formats](https://apireference.groupdocs.cloud/signature/#!/Helper/GetSupportedFormats) example.

## cURL Example ##



 Request

```html 
curl -v "https://api.groupdocs.cloud/v1/signature/formats" \
-X GET \
-H "Content-Type: application/json" \
-H "authorization: Bearer _0zqJ6w3enMdpEw5C6ZKm3lgYvHell1lHdx3vztekvBpCbZGqMvMplrKNrsVXih9Xe6738GSej2hb0BnwKVVz-ANEOnW0bGqjeiJcEySo2Y9-9VZ1K_rs_p4zZcsMoGNuDkL9G4rowGX9Wd1frChwRXzsJCpJUs9G5fGK-0kochaFTVdMgoOHU8JjUOQ5wiu-_ZQSbR0bMKRamxEyc_P_gv9NU7LTJQTCrP1SIJwem1WTX7GaTr8JRUYE0zsXH2vHUkJ1rNh-1RPblqE6wwrfxkklTCGxAWTxvoaSG-Ax-h2Zl9nZkBCAjS48zzz2kqIWS-K5WUmGPP9hAWQL00_deMB0Qi7xqvf2MWoJ831mFnyse-ZQ80fAqPyFBdYpS-xVFC0Uuc8rVHehydCxD0_oIJWkCU_GuDJpNMv6q4IpM-1RzFn"


 ```


 Response

```html 
{
  "formats": [
    {
      "fileFormat": "Portable Document Format",
      "extension": ".pdf"
    },
    {
      "fileFormat": "Microsoft Word",
      "extension": ".doc"
    },
    {
      "fileFormat": "Microsoft Word",
      "extension": ".docx"
    },
    {
      "fileFormat": "Microsoft Word",
      "extension": ".docm"
    },
    {
      "fileFormat": "Microsoft Word",
      "extension": ".dot"
    },
    {
      "fileFormat": "Microsoft Word",
      "extension": ".dotx"
    },
    {
      "fileFormat": "Microsoft Word",
      "extension": ".dotm"
    },
    {
      "fileFormat": "Microsoft Excel",
      "extension": ".xls"
    },
    {
      "fileFormat": "Microsoft Excel",
      "extension": ".xlsx"
    },
    {
      "fileFormat": "Microsoft Excel",
      "extension": ".xlsm"
    },
    {
      "fileFormat": "Microsoft Excel",
      "extension": ".xlsb"
    },
    {
      "fileFormat": "Microsoft PowerPoint",
      "extension": ".ppt"
    },
    {
      "fileFormat": "Microsoft PowerPoint",
      "extension": ".pptx"
    },
    {
      "fileFormat": "Microsoft PowerPoint",
      "extension": ".pps"
    },
    {
      "fileFormat": "Microsoft PowerPoint",
      "extension": ".ppsx"
    },
    {
      "fileFormat": "OpenDocument Formats",
      "extension": ".odt"
    },
    {
      "fileFormat": "OpenDocument Formats",
      "extension": ".ott"
    },
    {
      "fileFormat": "OpenDocument Formats",
      "extension": ".ods"
    },
    {
      "fileFormat": "OpenDocument Formats",
      "extension": ".odp"
    },
    {
      "fileFormat": "OpenDocument Formats",
      "extension": ".otp"
    },
    {
      "fileFormat": "OpenDocument Formats",
      "extension": ".ots"
    },
    {
      "fileFormat": "Rich Text Format",
      "extension": ".rtf"
    },
    {
      "fileFormat": "Plain Text File",
      "extension": ".txt"
    },
    {
      "fileFormat": "Comma-Separated Values",
      "extension": ".csv"
    },
    {
      "fileFormat": "HyperText Markup Language",
      "extension": ".html"
    },
    {
      "fileFormat": "HyperText Markup Language",
      "extension": ".mht"
    },
    {
      "fileFormat": "Extensible Markup Language",
      "extension": ".xml"
    },
    {
      "fileFormat": "XML Paper Specification",
      "extension": ".xps"
    },
    {
      "fileFormat": "Image files",
      "extension": ".bmp"
    },
    {
      "fileFormat": "Image files",
      "extension": ".gif"
    },
    {
      "fileFormat": "Image files",
      "extension": ".jpg"
    },
    {
      "fileFormat": "Image files",
      "extension": ".jpeg"
    },
    {
      "fileFormat": "Image files",
      "extension": ".png"
    },
    {
      "fileFormat": "Image files",
      "extension": ".tiff"
    },
    {
      "fileFormat": "Image files",
      "extension": ".djvu"
    },
    {
      "fileFormat": "Image files",
      "extension": ".webp"
    },
    {
      "fileFormat": "Electronic publication",
      "extension": ".epub"
    }
  ]
}
 
 ```




## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Get List of Supported File Formats ###



 C#




{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Supported_FileFormats.cs >}}





 PHP




{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Supported_FileFormats.php >}}





 Java




{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Supported_FileFormats.java >}}





 Python




{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Supported_FileFormats.py >}}





 Ruby




{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Supported_FileFormats.rb >}}




