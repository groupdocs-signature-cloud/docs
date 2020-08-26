---
id: "groupdocs-signature-cloud-20-7-release-notes"
url: "signature/groupdocs-signature-cloud-20-7-release-notes"
title: "GroupDocs.Signature Cloud 20.7 Release Notes"
productName: "GroupDocs.Signature Cloud"
weight: 2
description: ""
keywords: ""
---

{{< alert style="info" >}}
This page contains release notes for GroupDocs.Signature Cloud 20.7
{{< /alert >}}

## Major Features ##

* Added support for new file formats
* Added new signature properties
* New Update signatures API method
* New Delete signatures API method

## Full List of Issues Covering all Changes in this Release ##

|Key|Summary|Category
|---|---|---
|SIGNATURECLOUD-540|Add Properties to Signature as result of Search method|Improvement
|SIGNATURECLOUD-541|Implement Z-Order for Text Signature|Feature
|SIGNATURECLOUD-542|Implement Border for image signature|Feature
|SIGNATURECLOUD-543|Set up additional properties for digital signatures|Improvement
|SIGNATURECLOUD-544|Add support for new file formats|Improvement
|SIGNATURECLOUD-545|Update signature method|Feature
|SIGNATURECLOUD-546|Delete signature method|Feature

## Public API and Backward Incompatible Changes ##

### DocumentType option, property and enumeration type removed ###

There is no need to specify DocumentType property in all options of all API methods, the document type will be detected automatically from this version:

```javascript
SignOptions, VerifyOptions, SearchOptions, Signature
"DocumentType": "WordProcessing" * Removed, do not use
```

### Opacity option renamed to Transparency ###

BorderLine, SignBarcodeOptions, SignImageOptions, SignQRCodeOptions, SignDigitalOptions, SignStampOptions classes have been updated by renaming the Opacity property to Transparency with changing value interpretation, so value shell be set from 0.0 - no transparency (default) to 1.0 - transparent:

```javascript
BorderLine, SignBarcodeOptions, SignImageOptions, SignQRCodeOptions, SignDigitalOptions, SignStampOptions
"Transparency": 0.0
```

### Border options replaced with BorderLine class ###

SignOptions, VerifyOptions, SearchOptions and all inherited classes have been updated by removing BorderColor, BorderVisibility, BorderDashStyle, BorderWeight properties and replaced with single property Border, of existing BorderLine type:

```javascript
SignOptions, VerifyOptions, SearchOptions
"Border": {
   "Style": "Dash",
   "Color": { "Web": "Orange" },
   "Transparency": 0,
   "Weight": 12,
   "Visible": true
}
```

### ImageGuid and CertificateGuid renamed ###

SignImageOptions, SignStampOptions, SignDigitalOptions, TextureBrush classes have been updated by renaming the ImageGuid and CertificateGuid properties into ImageFilePath and CertificateFilePath:

```javascript
SignImageOptions, SignStampOptions, SignDigitalOptions, TextureBrush
"ImageFilePath": "file.jpg",
"CertificateFilePath": "cert.pfx"
```
