---
id: "overview"
url: "signature/overview"
title: "Overview"
productName: "GroupDocs.Signature Cloud"
weight: 1
description: ""
keywords: ""
---






# GroupDocs.Signature Cloud #

GroupDocs.Signature Cloud is a REST API to create, verify and search different type of Signatures objects to documents in the cloud by performing a wide variety of signature options you can wish to put on a document in the cloud, verify document and search Signatures in it.

{{< alert style="info" >}}
Summary there are five types of supported Signature type you can operate with.

* Text Signature - simple text label with different appearance settings and ability to align the signature location on page area, set font and colors, same as put on any or all pages of a document
* Image Signature - image signature with amount of filters and appearance settings, like Opacity, gray scale filter, brightness, contracts etc
* Barcode Signature - put different Barcode encode types on Document pages with lot of additional settings, appearance options and alignment properties
* QR-Code Signature - put different QR-Code encode types on Document pages with a lot of additional settings, appearance options and alignment properties
* Digital Signature - put digital signatures like certificate files (PFX, CRT format) on Document or separate pages (for PDF only) with a lot of additional settings, appearance options and alignment properties
* Stamp Signature - put Stamp generated images on Document pages

Our GroupDocs.Signature Cloud REST API allows the following operations with documents:

* Provide a list of supported document formats
* Obtain list of supported Barcode encode type names
* Obtain list of supported QR-Code encode type names
* Retrieve document properties like document size, creation and update dates, count of pages
* Retrieve document pages information like pages count, the size of each page
* Support adding all Signature types for PDF documents
* Support adding signature(except Digital Signature) to Image Document format (JPEG, PNG, BMP, GIF, multi frames TIFF)
* Support working with all Signature types (except Digital Signature for PowerPoint) on Microsoft Document formats like Word, Excel, PowerPoint
* Verify Text and Digital signatures for PDF, Word and Excel document types
* Verify Barcode and QR-Code Signatures for all document format types
* search Digital Signatures in PDF, SpreadSheet Document Formats and Word Processing Document Formats
* search Barcode and AR-Code Signatures in PDF, Images, SpreadSheet Document Formats, Word Processing Document Formats and Presentation Document Formats
{{< /alert >}}

## Supported File Formats ##

List of supported Document file formats:

| | | | | | | 
|---|---|---|---|---|---|---
|Supported formats / Signature Type|Text Signature|Stamp Signature|Image Signature|Digital Signature|Barcode Signature|QR-Code Signature
|Portable Document Format| | | | | | 
|PDF|+|+|+|+|+|+
|Microsoft Word| | | | | | 
|DOC – binary files|+|+|+|+|+|+
|DOCM|+|+|+|+|+|+
|DOCX – Open XML files|+|+|+|+|+|+
|DOT|+|+|+|+|+|+
|DOTM|+|+|+|+|+|+
|DOTX|+|+|+|+|+|+
|Microsoft Excel| | | | | | 
|XLS – binary files|+|+|+|+|+|+
|XLSB|+|+|+| |+| 
|XLSM|+|+|+|+|+|+
|XLSX – Open XML files|+|+|+|+|+|+
|XLT|+|+|+|+|+|+
|XLTM|+|+|+|+|+|+
|XLTX|+|+|+|+|+|+
|Microsoft PowerPoint| | | | | | 
|POT|+|+|+| |+| 
|POTM|+|+|+| |+| 
|POTX|+|+|+| 
|PPS|+|+|+| | | 
|PPSM|+|+|+| 
|PPSX|+|+|+| |+| 
|PPT – binary files|+|+|+| | | 
|PPTM| | | |+| | 
|PPTX – Open XML files|+|+|+|+|+| 
|OpenDocument Formats| | | | | | 
|ODT – OpenOffice Document|+|+|+|+|+| 
|ODP – OpenOffice Presentation|+|+|+| |+| 
|ODS – OpenOffice Spreadsheet|+|+|+| |+| 
|OTT – OpenOffice Text Template|+|+|+| |+|+
|Rich Text Format| | | | | | 
|RTF|+|+|+| |+|+
|**Image Format**| | | | | | 
|JPG|+|+|+| |+|+
|PNG|+|+|+| |+|+
|BMP|+|+|+| |+|+
|GIF|+|+|+| |+|+
|TIFF|+|+|+| |+|+


## Security and Authentication ##

The GroupDocs.Signature Cloud API is secured and requires authentication. Developers can [create]({{< ref "total/getting-started/ui-topics/create-new-app-and-get-app-key-and-sid.md" >}}) an app access key ID (appSID) and app secret access key when they [register]({{< ref "total/getting-started/ui-topics/creating-and-managing-account.md" >}}). Authenticated requests require a signature and AppSID query parameters or OAuth 2.0 authorization header. You can see complete detail [here]({{< ref "total/getting-started/overview-rest-api/authenticating-api-requests.md" >}}).

## SDKs ##

GroupDocs.Signature Cloud comes with SDKs for different platforms to use this REST API in your specific project effortlessly. Please checkout our GitHub [repository](https://github.com/groupdocs-signature-cloud) for a complete list of GroupDocs.Signature SDKs along with working examples, to get you started in no time.
|---|---

## API Explorer ##

The easiest way to try out our API right away in your browser! With the [GroupDocs for Cloud Web API explorer](https://apireference.groupdocs.cloud/signature/). This is a collection of Swagger documentation for the GroupDocs for Cloud APIs. You can get information about all the resources in the API. It also provides testing and interactivity to our API endpoint documentation.
|---|---
