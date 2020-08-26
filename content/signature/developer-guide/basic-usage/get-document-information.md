---
id: "get-document-information"
url: "signature/get-document-information"
title: "Get Document Information"
productName: "GroupDocs.Signature Cloud"
weight: 4
description: ""
keywords: ""
---

This API retrieves document information. It returns an object that contains information about file format, document pages and file size.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used to get [document information](https://apireference.groupdocs.cloud/signature/#/Info/GetInfo).

## cURL REST Example ##

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}} {{< tab tabNum="1" >}}

```javascript
 curl -X POST "https://api.groupdocs.cloud/v2.0/signature/info" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]" -H  "Content-Type: application/json" -d "{  \"FileInfo\": {    \"FilePath\": \"Signaturedocs/one-page.docx\",    \"StorageName\": \"MyStorage\",    \"VersionId\": \"\",    \"Password\": \"\"  }}"
```

{{< /tab >}} {{< tab tabNum="2" >}}

```javascript
{
  "fileName": "one-page.docx",
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
{{< /tab >}} {{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Get Document Information ###

{{< tabs tabTotal="6" tabID="10" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Python" tabName6="Ruby" >}} {{< tab tabNum="1" >}}

{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_DocumentInfo_File.cs >}}

{{< /tab >}} {{< tab tabNum="2" >}}

{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_DocumentInfo_File.java >}}

{{< /tab >}} {{< tab tabNum="3" >}}

{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Get_Document_Information.php >}}

{{< /tab >}} {{< tab tabNum="6" >}}

{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Get_Document_Information.rb >}}

{{< /tab >}} {{< tab tabNum="4" >}}

{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_DocumentInfo_File.js >}}

{{< /tab >}} {{< tab tabNum="5" >}}

{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_DocumentInfo_File.py >}}

{{< /tab >}} {{< /tabs >}}
