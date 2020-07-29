---
id: "signsettings"
url: "signature/signsettings"
title: "SignSettings"
productName: "GroupDocs.Signature Cloud"
weight: 4
description: ""
keywords: ""
---

# SignSettings #

SignSettings data structure used as input parameters for .

 

##### SignSettings example #####

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

##### SignSettings fields #####

|Name|Description|API Version
|---|---|---
|FileInfo.FilePath|The path of the document, located in the storage. **Required.**| 
|FileInfo.StorageName|Storage name| 
|FileInfo.VersionId|File version Id| 
|FileInfo.Password|Password for rendering password-protected documents| 
|SaveOptions.OverwriteExisting|Flag to remove existing file if it exists| 
|SaveOptions.OutputFilePath|Output flle path| 
|SaveOptions.SaveFormat|Output save format| 
|SignOptions|Array with at least one SignOptions that specifies Signature and Document type and its properties to be added to Document



| 
|---


 

 
