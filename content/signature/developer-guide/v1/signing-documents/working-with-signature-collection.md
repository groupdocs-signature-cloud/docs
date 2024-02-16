---
id: "working-with-signature-collection"
url: "signature/working-with-signature-collection"
title: "Working with Signature Collection"
productName: "GroupDocs.Signature Cloud"
weight: 7
description: ""
keywords: ""
toc: True
---

{{< alert style="info" >}}
Note:  The features listed on this page are supported only in GroupDocs.Signature Cloud V1
{{< /alert >}}

GroupDocs.Signature Cloud REST API supports to sign a document with multiple signatures. For example, you can add Text and Barcode Signature to a document at same time. To put list of signatures on document (Cells, Images, PDF, Slides or Words) Signature API provides an object **[SignOptionsCollectionData]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}})** that can contain one or more signature options. Please, use signature options which appropriate for current document format.

## Add Multiple Signatures to Document

You can create multiple Signatures on Document at same time provided by fileName and document folder (if required) using following API. It expects [SignOptionsCollectionData]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}) object data in request body. You can add required signature options to this object as per your document format.

It returns an object which contains document name, folder location and signing result.

### Resource

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add signature collection to a document](https://apireference.groupdocs.cloud/signature/#!/Signing/PostCollection).

### cURL example

{{< tabs "example1">}} {{< tab "Request" >}}

```javascript
curl --request POST \
--url http://api.groupdocs.cloud/v1/signature/01_pages.pdf/collection?folder#storage \
--header 'authorization: [Access Token]' \
--header 'content-type: application/json' \
--data '{ "items": [ { "barcodeTypeName": "Code39Standard", "borderVisiblity": true, "borderDashStyle": "Dash", "borderWeight": 12.0, "opacity": 0.8, "text": "123456789012", "left": 2, "top": 100, "width": 200, "height": 100, "locationMeasureType": "Pixels", "sizeMeasureType": "Pixels", "stretch": "None", "rotationAngle": 0, "horizontalAlignment": "Default", "verticalAlignment": "Default", "margin": { "all": 5, "left": 5, "top": 5, "right": 5, "bottom": 5 }, "marginMeasureType": "Pixels", "signAllPages": false, "font": { "fontFamily": "Times New Roman", "fontSize": 14.0, "bold": false, "italic": false, "underline": false }, "foreColor": { "Web": "DarkOrange" }, "borderColor": { "Web": "DarkOrange" }, "backgroundColor": { "Web": "BlueViolet" }, "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [  1 ] }, "OptionsType": "PdfSignBarcodeOptionsData" }, { "reason": "PdfDigitalReason", "contact": "PdfDigitalContact", "location": "PdfDigitalLocation", "visible": true, "password": "1234567890", "certificateGuid": "certificates\SherlockHolmes.pfx", "imageGuid": "images\signature_01.jpg", "left": 2, "top": 500, "width": 200, "height": 100, "locationMeasureType": "Pixels", "sizeMeasureType": "Pixels", "rotationAngle": 45, "horizontalAlignment": "Default", "verticalAlignment": "Default", "margin": { "all": 5, "left": 5, "top": 5, "right": 5, "bottom": 5 }, "marginMeasureType": "Pixels", "opacity": 0.9, "signAllPages": false, "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [  1 ] }, "OptionsType": "PdfSignDigitalOptionsData" } ] }'

```

{{< /tab >}} {{< tab "Response" >}}

```javascript
{
  "fileName": "01_pages.pdf",
  "folder": "Output",
  "code": 200,
  "status": "OK"
}
```

{{< /tab >}} {{< /tabs >}}

### SDK examples

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](/signature/available-sdks).

{{< tabs "example2">}} {{< tab "C#" >}}

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Signature_Collection.cs >}}

{{< /tab >}} {{< tab "PHP" >}}

{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_Collection.php >}}

{{< /tab >}} {{< tab "Java" >}}

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Signature_Collection.java >}}

{{< /tab >}} {{< tab "Python" >}}

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Signature_Collection.py >}}

{{< /tab >}} {{< tab "Ruby" >}}

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Signature_Signature_Collection.rb >}}

{{< /tab >}} {{< /tabs >}}

## Add Multiple Signatures to Document at Provided URL

You can create multiple Signatures on Document at same time provided by specified file URL and document folder (if required) using following API. It expects [SignOptionsCollectionData]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}) object data in request body. You can add required signature options to this object as per your document format.

It returns an object which contains document name, folder location and signing result.

### Resource

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add signature collection to a document at provided url](https://apireference.groupdocs.cloud/signature/#!/Signing/PostCollectionFromUrl).

### cURL example

{{< tabs "example3">}} {{< tab "Request" >}}

```javascript
curl --request POST \
--url http://api.groupdocs.cloud/v1/signature/collection/verification?url#https%3a%2f%2fwww.dropbox.com%2fs%2fumokluz338w4ng7%2fone-page.docx%3fdl%3d1 \
--header 'authorization: [Access Token]' \
--header 'content-type: application/json' \
--data '{ "items": [ { "barcodeTypeName": "Code39Standard", "borderVisiblity": true, "borderDashStyle": "Dash", "borderWeight": 12.0, "opacity": 0.8, "text": "123456789012", "left": 2, "top": 100, "width": 200, "height": 100, "locationMeasureType": "Pixels", "sizeMeasureType": "Pixels", "stretch": "None", "rotationAngle": 0, "horizontalAlignment": "Default", "verticalAlignment": "Default", "margin": { "all": 5, "left": 5, "top": 5, "right": 5, "bottom": 5 }, "marginMeasureType": "Pixels", "signAllPages": false, "font": { "fontFamily": "Times New Roman", "fontSize": 14.0, "bold": false, "italic": false, "underline": false }, "foreColor": { "Web": "DarkOrange" }, "borderColor": { "Web": "DarkOrange" }, "backgroundColor": { "Web": "BlueViolet" }, "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [  1 ] }, "OptionsType": "PdfSignBarcodeOptionsData" }, { "reason": "PdfDigitalReason", "contact": "PdfDigitalContact", "location": "PdfDigitalLocation", "visible": true, "password": "1234567890", "certificateGuid": "certificates\SherlockHolmes.pfx", "imageGuid": "images\signature_01.jpg", "left": 2, "top": 500, "width": 200, "height": 100, "locationMeasureType": "Pixels", "sizeMeasureType": "Pixels", "rotationAngle": 45, "horizontalAlignment": "Default", "verticalAlignment": "Default", "margin": { "all": 5, "left": 5, "top": 5, "right": 5, "bottom": 5 }, "marginMeasureType": "Pixels", "opacity": 0.9, "signAllPages": false, "documentPageNumber": 1, "pagesSetup": { "firstPage": true, "lastPage": false, "oddPages": false, "evenPages": false, "pageNumbers": [  1 ] }, "OptionsType": "PdfSignDigitalOptionsData" } ] }'

```

{{< /tab >}} {{< tab "Response" >}}

```javascript
{
  "fileName": "01_pages.pdf",
  "folder": "Output",
  "code": 200,
  "status": "OK"
}
```

{{< /tab >}} {{< /tabs >}}

### SDK examples

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](/signature/available-sdks).

{{< tabs "example4">}} {{< tab "C#" >}}

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Signature_Collection_FromUrl.cs >}}

{{< /tab >}} {{< tab "PHP" >}}

{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_Collection_URL.php >}}

{{< /tab >}} {{< tab "Java" >}}

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Signature_Collection_FromUrl.java >}}

{{< /tab >}} {{< tab "Python" >}}

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Signature_Collection_FromUrl.py >}}

{{< /tab >}} {{< tab "Ruby" >}}

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Signature_Signature_Collection_FromUrl.rb >}}

{{< /tab >}} {{< /tabs >}}

