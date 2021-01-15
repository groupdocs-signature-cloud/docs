---
id: "overview"
url: "signature/overview"
title: "Overview"
productName: "GroupDocs.Signature Cloud"
weight: 1
description: ""
keywords: ""
---

GroupDocs.Signature Cloud is a REST API to create, verify, search, update and delete different type of Signatures objects to documents in the cloud by performing a wide variety of signature options you can wish to put on a document in the cloud, verify document and search Signatures in it.

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
* Search Digital Signatures in PDF, SpreadSheet Document Formats and Word Processing Document Formats
* Search Barcode and AR-Code Signatures in PDF, Images, SpreadSheet Document Formats, Word Processing Document Formats and Presentation Document Formats
* Update signatures by ID
* Delete signatures by ID
{{< /alert >}}

## Supported File Formats

List of supported Document file formats:

|Supported formats / Signature Type|Text Signature|Stamp Signature|Image Signature|Digital Signature|Barcode Signature|QR-Code Signature|
|---|---|---|---|---|---|---|
|Portable Document Format| | | | | |
|[PDF](https://docs.fileformat.com/pdf/)|+|+|+|+|+|+
|Microsoft Word| | | | | |
|[DOC](https://docs.fileformat.com/word-processing/doc/)|+|+|+|+|+|+
|[DOCM](https://docs.fileformat.com/word-processing/docm/)|+|+|+|+|+|+
|[DOCX](https://docs.fileformat.com/word-processing/docx/)|+|+|+|+|+|+
|[DOT](https://docs.fileformat.com/word-processing/dot/)|+|+|+|+|+|+
|[DOTM](https://docs.fileformat.com/word-processing/dotm/)|+|+|+|+|+|+
|[DOTX](https://docs.fileformat.com/word-processing/dotx/)|+|+|+|+|+|+
|Microsoft Excel| | | | | |
|[XLS](https://docs.fileformat.com/spreadsheet/xls/)|+|+|+|+|+|+
|[XLSB](https://docs.fileformat.com/spreadsheet/xlsb/)|+|+|+| |+|
|[XLSM](https://docs.fileformat.com/spreadsheet/xlsm/)|+|+|+|+|+|+
|[XLSX](https://docs.fileformat.com/spreadsheet/xlsx/)|+|+|+|+|+|+
|[XLT](https://docs.fileformat.com/spreadsheet/xlt/)|+|+|+|+|+|+
|[XLTM](https://docs.fileformat.com/spreadsheet/xltm/)|+|+|+|+|+|+
|[XLTX](https://docs.fileformat.com/spreadsheet/xltx/)|+|+|+|+|+|+
|Microsoft PowerPoint| | | | | |
|[POT](https://docs.fileformat.com/presentation/pot/)|+|+|+| |+|
|[POTM](https://docs.fileformat.com/presentation/potm/)|+|+|+| |+|
|[POTX](https://docs.fileformat.com/presentation/potx/)|+|+|+|
|[PPS](https://docs.fileformat.com/presentation/pps/)|+|+|+| | |
|[PPSM](https://docs.fileformat.com/presentation/ppsm/)|+|+|+|
|[PPSX](https://docs.fileformat.com/presentation/ppsx/)|+|+|+| |+|
|[PPT](https://docs.fileformat.com/presentation/ppt/)|+|+|+| | |
|[PPTM](https://docs.fileformat.com/presentation/pptm/)| | | |+| |
|[PPTX](https://docs.fileformat.com/presentation/pptx/)|+|+|+|+|+|
|OpenDocument Formats| | | | | |
|[ODT](https://docs.fileformat.com/word-processing/odt/)|+|+|+|+|+|
|[ODP](https://docs.fileformat.com/presentation/odp/)|+|+|+| |+|
|[ODS](https://docs.fileformat.com/spreadsheet/ods/)|+|+|+| |+|
|[OTT](https://docs.fileformat.com/word-processing/ott/)|+|+|+| |+|+
|Rich Text Format| | | | | |
|[RTF](https://docs.fileformat.com/word-processing/rtf/)|+|+|+| |+|+
|**Image Formats**| | | | | |
|[JPG](https://docs.fileformat.com/image/jpeg/)|+|+|+| |+|+
|[PNG](https://docs.fileformat.com/image/png/)|+|+|+| |+|+
|[BMP](https://docs.fileformat.com/image/bmp/)|+|+|+| |+|+
|[GIF](https://docs.fileformat.com/image/gif/)|+|+|+| |+|+
|[TIFF](https://docs.fileformat.com/image/tiff/)|+|+|+| |+|+
|[CDR](https://docs.fileformat.com/image/cdr/)|+|+|+| |+|+

## Security and Authentication

The GroupDocs.Signature Cloud API is secured and requires authentication.

Developers can [create]({{< ref "total/getting-started/ui-topics/creating-and-managing-application.md" >}}) an Application which has a Client Id and Client Secret when they [register]({{< ref "total/getting-started/ui-topics/creating-and-managing-account.md" >}}).

Authenticated requests require an OAuth 2.0 authorization header. You can see complete detail [here]({{< ref "total/getting-started/overview-rest-api/authenticating-api-requests.md" >}}).

## SDKs

GroupDocs.Signature Cloud comes with SDKs for different platforms to use this REST API in your specific project effortlessly. Please checkout our GitHub [repository](https://github.com/groupdocs-signature-cloud) for a complete list of GroupDocs.Signature SDKs along with working examples, to get you started in no time.

## API Explorer

The easiest way to try out our API right away in your browser! With the [GroupDocs for Cloud Web API explorer](https://apireference.groupdocs.cloud/signature/). This is a collection of Swagger documentation for the GroupDocs for Cloud APIs. You can get information about all the resources in the API. It also provides testing and interactivity to our API endpoint documentation.
