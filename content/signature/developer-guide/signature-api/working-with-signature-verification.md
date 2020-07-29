---
id: "working-with-signature-verification"
url: "signature/working-with-signature-verification"
title: "Working with Signature Verification"
productName: "GroupDocs.Signature Cloud"
weight: 2
description: ""
keywords: ""
---






# Verify Barcode Signature in a Document #

GroupDocs.Signature Cloud REST API supports to verify a signed document. It provides methods to verify Barcode Signature in Documents Pages with different options for page number, text and search criteria by using [Verification Options Objects]({{< ref "signature/developer-guide/data-structures/verifysettings.md" >}})) data in request body.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to verify Barcode signature in a document](https://apireference.groupdocs.cloud/signature/#/Sign/VerifySignatures).

## cURL Example ##





 Request

```html 
curl -X POST "https://api.groupdocs.cloud/v2.0/signature/verify" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]" -H  "Content-Type: application/json" -d "{  \"FileInfo\": {    \"FilePath\": \"signed/Signed_BarCode.pdf\",    \"StorageName\": \"MyStorage\",    \"VersionId\": \"\",    \"Password\": \"\",      },     \"VerifyOptions\": [        {           \"DocumentType\": \"Pdf\",           \"SignatureType\": \"Text\",             \"Page\": 1,           \"Text\": \"John\",           \"MatchType\": \"Contains\"        }    ] }      }    }  ]}"

 ```




 Response

```html 
{
  "FileInfo": {
    "FilePath": "Signed_BarCode.pdf"
  },
  "Size" : 12345,
  "IsSuccess": "true"
}



 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Verify Barcode Signature in a Document ###





 C#




{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Verify_Barcode_Signature.cs >}}







 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Verify_Barcode_Signature.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Verify_Barcode_Signature.php >}}







 Ruby




{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Verify_Barcode_Signature.rb >}}







 Node




{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Verify_Barcode_Signature.js >}}







 Python




{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Verify_Barcode_Signature.py >}}









# Verify Digital Signature in a Document #

GroupDocs.Signature Cloud REST API supports to verify a signed document. It provides methods to verify Digital Signature in Documents Pages with different options for page number, text and search criteria by using [Verification Options Objects]({{< ref "signature/developer-guide/data-structures/verifysettings.md" >}})) data in request body.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used [to verify Digital signature in a document](https://apireference.groupdocs.cloud/signature/#/Sign/VerifySignatures) example.

## cURL Example ##





 Request

```html 
curl -X POST "https://api.groupdocs.cloud/v2.0/signature/verify" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]" -H  "Content-Type: application/json" -d "{  \"FileInfo\": {    \"FilePath\": \"signed/Signed_BarCode.pdf\",    \"StorageName\": \"MyStorage\",    \"VersionId\": \"\",    \"Password\": \"\",      },     \"VerifyOptions\": [        {           \"DocumentType\": \"Pdf\",           \"SignatureType\": \"digital\",             \"Page\": 1,           \"Text\": \"John\",           \"MatchType\": \"Contains\"        }    ] }      }    }  ]}"

 ```




 Response

```html 
{
  "result": true,
  "fileName": "Signed_Digital.pdf",
  "folder": "signed",
  "code": 200,
  "status": "OK"
}
 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Verify Digital Signature in a Document ###





 C#




{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Verify_Digital_Signature.cs >}}







 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Verify_Digital_Signature.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Verify_Digital_Signature.php >}}







 Ruby




{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Verify_Digital_Signature.rb >}}







 Node




{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Verify_Digital_Signature.js >}}







 Python




{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Verify_Digital_Signature.py >}}









# Verify QRCode Signature in a Document #

GroupDocs.Signature Cloud REST API supports to verify a signed document. It provides methods to verify QRCode Signature in Documents Pages with different options for page number, text and search criteria by using [Verification Options Objects]({{< ref "signature/developer-guide/data-structures/verifysettings.md" >}})) data in request body.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used [to verify QRCode signature in a document](https://apireference.groupdocs.cloud/signature/#/Sign/VerifySignatures) example.

## cURL Example ##





 Request

```html 
curl -X POST "https://api.groupdocs.cloud/v2.0/signature/verify" -H "accept: application/json" -H "authorization: Bearer [Access Token]" -H "Content-Type: application/json" -d "{ \"FileInfo\": { \"FilePath\": \"signed/Signed_BarCode.pdf\", \"StorageName\": \"MyStorage\", \"VersionId\": \"\", \"Password\": \"\", }, \"VerifyOptions\": [ { \"DocumentType\": \"Pdf\", \"SignatureType\": \"qrcode\", \"Page\": 1, \"Text\": \"John\", \"MatchType\": \"Contains\" } ] } } } ]}"
 ```




 Response

```html 
{
  "result": true,
  "fileName": "Signed_QRCode.pdf",
  "folder": "signed",
  "code": 200,
  "status": "OK"
}
 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Verify QRCode Signature in a Document ###





 C#




{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Verify_QRCode_Signature.cs >}}







 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Verify_QRCode_Signature.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Verify_QRCode_Signature.php >}}







 Ruby




{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Verify_QRCode_Signature.rb >}}







 Node




{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Verify_QRCode_Signature.js >}}







 Python




{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Verify_QRCode_Signature.py >}}









# Verify Text Signature in a Document #

GroupDocs.Signature Cloud REST API supports to verify a signed document. It provides methods to verify Text Signature in Documents Pages with different options for page number, text and search criteria by using [Verification Options Objects]({{< ref "signature/developer-guide/data-structures/verifysettings.md" >}})) data in request body.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used [to verify Text signature in a document](https://apireference.groupdocs.cloud/signature/#/Sign/VerifySignatures) example.

## cURL Example ##





 Request

```html 
curl -X POST "https://api.groupdocs.cloud/v2.0/signature/verify" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]" -H  "Content-Type: application/json" -d "{  \"FileInfo\": {    \"FilePath\": \"signed/Signed_BarCode.pdf\",    \"StorageName\": \"MyStorage\",    \"VersionId\": \"\",    \"Password\": \"\",      },     \"VerifyOptions\": [        {           \"DocumentType\": \"Pdf\",           \"SignatureType\": \"Text\",             \"Page\": 1,           \"Text\": \"John\",           \"MatchType\": \"Contains\"        }    ] }      }    }  ]}"

 ```




 Response

```html 
{
  "result": true,
  "fileName": "Signed_Text.pdf",
  "folder": "signed",
  "code": 200,
  "status": "OK"
}
 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Verify Text Signature in a Document ###





 C#




{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Verify_Text_Signature.cs >}}







 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Verify_Text_Signature.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Verify_Text_Signature.php >}}







 Ruby




{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Verify_Text_Signature.rb >}}







 Node




{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Verify_Text_Signature.js >}}







 Python




{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Verify_Text_Signature.py >}}









# Verify Multiple Signatures to Document #

GroupDocs.Signature Cloud REST API supports to verify multiple signatures in a document. For example, you can verify whether a document contains Text and Barcode Signatures at same time. To verify list of signatures on document (Cells, Images, PDF, Slides or Words) Signature API provides an object **[VerifyOptionsCollectionData]({{< ref "signature/developer-guide/data-structures/verifysettings.md" >}}))** that can contain one or more verify options. Please, use verify options which appropriate for current document format.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to verify document with multiple signatures](https://apireference.groupdocs.cloud/signature/#/Sign/VerifySignatures).

## cURL Example ##





 Request

```html 
curl -X POST "https://api.groupdocs.cloud/v2.0/signature/verify" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]" -H  "Content-Type: application/json" -d "{  \"FileInfo\": {    \"FilePath\": \"signed/Signed_BarCode.pdf\",    \"StorageName\": \"MyStorage\",    \"VersionId\": \"\",    \"Password\": \"\",      },     \"VerifyOptions\": [        {           \"DocumentType\": \"Pdf\",           \"SignatureType\": \"Text\",             \"Page\": 1,           \"Text\": \"John\",           \"MatchType\": \"Contains\"        }    ] }      }    }  ]}"


 ```




 Response

```html 
{
  "result": true,
  "fileName": "SignedForVerificationAll.pdf",
  "folder": "pdf",
  "code": 200,
  "status": "OK"
}
 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Verify Multiple Signatures ###





 C#




{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Verify_Collection_Signature.cs >}}







 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Verify_Collection_Signature.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Verify_Collection_Signature.php >}}







 Ruby




{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Verify_Collection_Signature.rb >}}







 Node




{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Verify_Collection_Signature.js >}}







 Python




{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Verify_Collection_Signature.py >}}







