---
id: "signature-api"
url: "signature/signature-api"
title: "Working with Signature API"
productName: "GroupDocs.Signature Cloud"
weight: 13
description: ""
keywords: ""
---

## Signature API ##

This API intended for creating signatures in the document based on passed array of signature options. After getting response, rendering document can be downloaded using provided URLs or paths.

#### URI ####

```html 

~/create

 ```

#### HTTP POST ####

#### Example 5 (Create signature) ####

Takes [SignSettings ]({{< ref "signature/developer-guide/data-structures/signsettings.md" >}}))as input and returns [SignResult]({{< ref "signature/developer-guide/data-structures/signresult.md" >}})).

###### Example URL ######

```html 

https://api.groupdocs.cloud/v2.0/signature/create

 ```

###### Example Request  ######

```html 

{
  "FileInfo": {
    "FilePath": "files01.docx",
  }, 
  "SaveOptions": {
    "OverwriteExisting": "true",
    "OutputFilePath": "file02.docx",
    "SaveFormat": "docx"
  },
  "SignOptions": 
  [
    {
      "DocumentType": "WordProcessing",
      "SignatureType": "Barcode",  
      "Page": 1,
      "Text": "John Smith",
      "BarcodeType": "Code128",
      "Left": 2,
      "Top": 2
    },
    {
      "DocumentType": "WordProcessing",
      "SignatureType": "Image",  
      "Page": 1,
      "ImageGuid": "image1.jpg",
      "Left": 200,
      "Top": 200,
      "Opacity": 0.5
    }
    ]
 }

 ```

###### Example Response ######

```html 

{
  "FileInfo": {
    "FilePath": "files01.docx"
  },
  "Size" : 12345,
  "DownloadUrl": "signed/ofiles01.docx"
}



 ```

## Verify signature API ##

This API intended for verifying signatures in the document based on passed array of verification options. Response will contain result of verification.

#### URI ####

```html 

~/verify

 ```

#### HTTP POST ####

#### Example 6 (Verify signatures in document) ####

Takes [VerifySettings ]({{< ref "signature/developer-guide/data-structures/verifysettings.md" >}}))as input and returns [VerifyResult]({{< ref "signature/developer-guide/data-structures/verifyresult.md" >}})).

###### Example URL ######

```html 

https://api.groupdocs.cloud/v2.0/signature/verify

 ```

###### Example Request  ######

```html 

{
  "FileInfo": {
    "FilePath": "string",
    "StorageName": "string",
    "VersionId": "string",
    "Password": "string"
  },   
  "VerifyOptions": [
        {
           "DocumentType": "Pdf",
           "SignatureType": "Text",  
           "Page": 1,
           "Text": "John",
           "MatchType": "Contains"
        }
    ]
 }



 ```

###### Example Response ######

```html 

{
  "FileInfo": {
    "FilePath": "file01.pdf"
  },
  "Size" : 12345,
  "IsSuccess": "true"
}



 ```

 

## Search signature API ##

This API intended for search for signatures in the document. Response will contain array of found signatures.

#### URI ####

```html 

~/search

 ```

#### HTTP POST ####

#### Example 7 (Search for signatures in document) ####

Takes [SearchSettings ]({{< ref "signature/developer-guide/data-structures/searchsettings.md" >}}))as input and returns [SearchResult]({{< ref "signature/developer-guide/data-structures/searchresult.md" >}})).

###### Example URL ######

```html 

https://api.groupdocs.cloud/v2.0/signature/search

 ```

###### Example Request  ######

```html 

{
  "FileInfo": {
    "FilePath": "string",
    "StorageName": "string",
    "VersionId": "string",
    "Password": "string"
  },   
  "SearchOptions": 
   [
    {
        "DocumentType": "Pdf",
        "SignatureType": "Barcode",  
        "Page": 1,
        "Text": "123",
        "BarcodeType": "Code128",
        "MatchType": "Contains"
    }
   ]
 }



 ```

###### Example Response ######

```html 

{
  "FileInfo": {
    "FilePath": "fiel01.pdf"
  },
  "Size" : 12345,
  "Signatures": 
  [
    {
       "DocumentType": "Pdf",
       "SignatureType": "Barcode",  
       "BarcodeType": "Code128",
       "Text": "1223344545454"
    }
   ]
}



 ```