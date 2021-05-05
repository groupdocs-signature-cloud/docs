---
id: "groupdocs-signature-cloud-21-5-release-notes"
url: "signature/groupdocs-signature-cloud-21-5-release-notes"
title: "GroupDocs.Signature Cloud 21.5 Release Notes"
productName: "GroupDocs.Signature Cloud"
weight: 1
description: ""
keywords: ""
---

{{< alert style="info" >}}
This page contains release notes for GroupDocs.Signature Cloud 21.5
{{< /alert >}}

## Major Features ##

* Add document preview API
* Added new sign options signature properties

## Full List of Issues Covering all Changes in this Release ##

|Key|Summary|Category
|---|---|---
|SIGNATURECLOUD-571|Add document preview API|Feature
|SIGNATURECLOUD-569|Add SignTextOptions.Native option|Feature
|SIGNATURECLOUD-570|Add PDF digital signature properties|Feature

## Public API and Backward Incompatible Changes ##

### Add document preview API ###

Method allows to create document preview images, one per page. Image size and format can be set as options.

Input data structure: PreviewSettings
Output data structure: PreviewResult

```javascript
/signature/preview
```

### Added SignTextOptions.Native option ###

Gets or sets the native attribute. If it is set document specific signatures
could be used. Native text watermark for WordProcessing documents is different
than regular, for example.

```javascript
SignTextOptions
"Options": [{
   ...
   "Native": true
}]
```

### Added PDF digital signature properties ###

DigitalSignature was expanded with pdf digital signature properties

```javascript
DigitalSignature
"Options": {
   ...
   "PdfDigitalSignature": {
       "ContactInfo": "string",
       "Location": "string",
       "Reason": "string",
       "Type": "enum",
       "TimeStamp": "TimeStamp",
       "ShowProperties": "boolean"
   }
}
```
