---
id: "search-digital-signature"
url: "signature/search-digital-signature"
title: "Search Digital Signature"
productName: "GroupDocs.Signature Cloud"
weight: 2
description: ""
keywords: ""
---

{{< alert style="info" >}}
Note:  The features listed on this page are supported only in GroupDocs.Signature Cloud V1
{{< /alert >}}

# Introduction #

GroupDocs.Signature Cloud REST API supports to search Digital signatures in supported document formats. It provides method to search Digital Signature in Document Pages with different options by using [Search Options Object]({{< ref "signature/developer-guide/v1/common-resources/search-options-objects.md" >}}) data in request body.

# Search Digital Signature #

You can search Digital Signature on Document provided by fileName and document folder (if required) using following API. It expects [Search Options Object]({{< ref "signature/developer-guide/v1/common-resources/search-options-objects.md" >}}) data in request body.

It returns an object which contains document name, folder location and search result.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to search Digital signature in a document](https://apireference.groupdocs.cloud/signature/#!/Search/PostSearchDigital).

## cURL Example ##

 Request

```javascript
curl --request POST \
--url http://api.groupdocs.cloud/v1/signature/SignedForVerificationAll.xlsx/digital/search?folder#signed \
--header 'authorization: [Access Token]' \
--header 'content-type: application/json' \
--data '{ "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [ 1 ] }, "searchAllPages": true, "OptionsType": "CellsSearchDigitalOptionsData" }'

```

 Response

```javascript
{
  "signatures": [
    {
      "comments": "Test comment",
      "isValid": false,
      "digitalSignatureType": 0,
      "signTime": "2017-01-25T10:41:54Z",
      "signatureType": "CellsDigitalSignatureData"
    }
  ],
  "fileName": "SignedForVerificationAll.xlsx",
  "folder": "cells",
  "code": 200,
  "status": "OK"
}
```

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Search Digital Signature in a Document ###

 C#

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Search_Signature_Digital.cs >}}

 PHP

{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Digital_Search.php >}}

 Java

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Search_Signature_Digital.java >}}

 Python

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Search_Signature_Digital.py >}}

 Ruby

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Search_Signature_Digital.rb >}}

# Search Digital Signature in a Document at Provided URL #

You can search Digital Signature for document at provided URL with [Search Options]({{< ref "signature/developer-guide/v1/common-resources/search-options-objects.md" >}}) by using following API. It retrieves file from specified URL and tries to detect file type when fileName parameter is not specified.

It expects[ Search Options]({{< ref "signature/developer-guide/v1/common-resources/search-options-objects.md" >}}) object data in request body. Based on passed Search Options settings proceeds with Document search, it returns object which contains result of searching process. The field Signatures keeps list of objects which represents found signatures like WordsDigitalSignatureData.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to search Digital signature in a document at provided URL](https://apireference.groupdocs.cloud/signature/#!/Search/PostSearchBarcodeFromUrl).

## cURL Example ##

 Request

```javascript
curl --request POST \
--url http://api.groupdocs.cloud/v1/signature/digital/search?url#https%3a%2f%2fwww.dropbox.com%2fs%2fumokluz338w4ng7%2fone-page.docx%3fdl%3d1 \
--header 'authorization: [Access Token]' \
--header 'content-type: application/json' \
--data '{ "DocumentPageNumber": 1,  "Password" : "1234567890",  "CertificateGuid": "mrjohn.smith.crt",  "OptionsType" : "WordsSearchDigitalOptionsData" }'

```

 Response

```javascript
{
  "fileName": "one-page.docx",
  "folder": "Output",
  "Code": "OK",
  "Status" : "OK",
  "Signatures" : [
    { Comments: "Comment#1", IsValid: "true", SignatureType: "CryptoApi", SignTime: "2017-01-01" },
    { Comments: "Comment#2", IsValid: "false", SignatureType: "XmlDsig", SignTime: "2017-10-10" }
    ]
}
```

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Search Digital Signature in a Document at provided URL ###

 C#

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Search_Signature_Digital_URL.cs >}}

 PHP

{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Digital_Search_URL.php >}}

 Java

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Search_Signature_Digital_URL.java >}}

 Python

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Search_Signature_Digital_URL.py >}}

 Ruby

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Search_Signature_Digital_URL.rb >}}

