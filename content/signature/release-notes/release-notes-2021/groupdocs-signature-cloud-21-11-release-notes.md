---
id: "groupdocs-signature-cloud-21-11-release-notes"
url: "signature/groupdocs-signature-cloud-21-11-release-notes"
title: "GroupDocs.Signature Cloud 21.11 Release Notes"
productName: "GroupDocs.Signature Cloud"
weight: 1
description: ""
keywords: ""
---

{{< alert style="info" >}}
This page contains release notes for GroupDocs.Signature Cloud 21.11
{{< /alert >}}

## Major Features ##

* Added new options describing signature appearance
* Added support of FormField signatures
* Improved getting document info with signatures list and new options

## Full List of Issues Covering all Changes in this Release ##

|Key|Summary|Category
|---|---|---
|SIGNATURECLOUD-587|Add support for SignOptions.Appearance|Improvement
|SIGNATURECLOUD-588|Implement ability to exclude Deleted Signatures from Document information|Feature
|SIGNATURECLOUD-589|Extend IDocumentInfo interface with new property to keep list of all existing Signatures|Improvement
|SIGNATURECLOUD-590|Extend Delete method with overloads that accept Id or List of identifiers|Investigation

## Public API and Backward Incompatible Changes ##

### Get document info API ###

InfoSettings was extended with ShowDeletedSignaturesInfo property that
that allow to include deleted signatures into Document Info result

```javascript
{
   "FileInfo": {
      "FilePath": "one-page.docx"
   },
   "ShowDeletedSignaturesInfo": true
}
```

InfoResult was extended with Signatures field that
contains collection of document signatures

```javascript
{
   ...
 "signatures": [
    {
      "text": "John Smith",
      "signatureImplementation": "Native",
      "signatureType": "Text",
      "pageNumber": 1,
      "signatureId": "9701c793-a548-444c-9625-91bc5ae0a474",
      "isSignature": true,
      "createdOn": "2020-07-07T05:59:57.4849682+00:00",
      "modifiedOn": "2020-07-07T05:59:57.4849682+00:00",
      "top": 330,
      "left": 2,
      "width": 200,
      "height": 100
    },
    ...
}
```

### Added SignOptions.Appearance option ###

SignOptions (and derived structures) was extended with new option
Appearance with additional properties for this options instance

```javascript
{
  "FileInfo": {
    "FilePath": "string",
    "StorageName": "string",
    "VersionId": "string",
    "Password": "string"
  },
  "Options": [
    {
      "Page": 0,
      "AllPages": true,
      "PagesSetup": {
        "FirstPage": true,
        "LastPage": true,
        "OddPages": true,
        "EvenPages": true,
        "PageNumbers": [
          0
        ]
      },
      "Appearance": {}
    }
  ],
  "SaveOptions": {
    "OverwriteExisting": true,
    "OutputFilePath": "string",
    "SaveFormat": "string"
  }
}
```

There are several derived structures of SignatureAppearance:
PdfTextAnnotationAppearance,
PdfTextStickerAppearance,
ImageAppearance,
DigitalSignatureAppearance,
PdfDigitalSignatureAppearance

### Added FormField signature type ###

The SignatureType enum was extended with new FormField value.
Added new signature classes:
CheckboxFormFieldSignature,
ComboboxFormFieldSignature,
DigitalFormFieldSignature,
RadioButtonFormFieldSignature,
TextFormFieldSignature
