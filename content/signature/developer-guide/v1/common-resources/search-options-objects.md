---
id: "search-options-objects"
url: "signature/search-options-objects"
title: "Search Options Objects"
productName: "GroupDocs.Signature Cloud"
weight: 3
description: ""
keywords: ""
toc: True
---

{{< alert style="info" >}}
Note:  The features listed in this page are supported only in GroupDocs.Signature Cloud V1
{{< /alert >}}

Page contains description for Search Options objects and object properties

## SearchOptionsCollectionData Object

Provides list of options for documents searching.

Example SearchOptionsCollectionData object

```javascript
{
  "items": [
    {
      "barcodeTypeName": "Code39Standard",
      "text": "123456789012",
      "matchType": "Contains",
      "documentPageNumber": 3,
      "pagesSetup": {
        "firstPage": false,
        "lastPage": true,
        "oddPages": false,
        "evenPages": true,
        "pageNumbers": [
          1,
          3,
          5
        ]
      },
      "searchAllPages": true
    },
    {
      "documentPageNumber": 3,
      "pagesSetup": {
        "firstPage": false,
        "lastPage": true,
        "oddPages": false,
        "evenPages": true,
        "pageNumbers": [
          1,
          3,
          5
        ]
     }
  ]
}
```

 SearchOptionsCollectionData Object Fields

|Name|Type|Description
|---|---|---
|Items|List<SearchOptionsData>|List of Search Options records.

## CellsSearchBarcodeOptionsData Object

Provides options to search Barcode Signature in Cells Documents.

Example CellsSearchBarcodeOptionsData object

```javascript
{
  "BarcodeTypeName": "Code128",
  "Text": "John Smith",
  "MatchType": "Contains",
  "DocumentPageNumber": 1,
  "PagesSetup": {
    "FirstPage": false,
    "LastPage": true,
    "OddPages": false,
    "EvenPages": true,
    "PageNumbers": [
      1,
      3,
      5
    ]
  },
  "SearchAllPages": true,
  "OptionsType": "CellsSearchBarcodeOptionsData"
}
```

 CellsSearchBarcodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|BarcodeTypeName|string|Optional Barcode Type name (value one of supported Barcode Type names) to search Barcodes with exact Type. When value is not set no Type criteria.
|Text|string|Optional. Specifies text to search in Barcodes. If value is not set there will be no Text criteria.
|MatchType|enum|Specifies Text matching logic.
|DocumentPageNumber|int|Specifies document-sheet page number to search Barcode Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|SearchAllPages|bool|The flag to search all pages in document
|OptionsType|string|The class name of options object, should always contains value "CellsSearchBarcodeOptionsData". This property is set automatically when using SDK classes.

## ImagesSearchBarcodeOptionsData Object

Provides options to search Barcode Signature in Images Documents.

Example ImagesSearchBarcodeOptionsData object

```javascript
{
  "barcodeTypeName": "Code39Standard",
  "text": "123456789012",
  "matchType": "Contains",
  "documentPageNumber": 3,
  "pagesSetup": {
    "firstPage": false,
    "lastPage": true,
    "oddPages": false,
    "evenPages": true,
    "pageNumbers": [
      1,
      3,
      5
    ]
  },
  "searchAllPages": true,
  "optionsType": "ImagesSearchBarcodeOptionsData"
}
```

 ImagesSearchBarcodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|BarcodeTypeName|string|Optional Barcode Type name (value one of supported Barcode Type names) to search Barcodes with exact Type. When value is not set no Type criteria.
|Text|string|Optional. Specifies text to search in Barcodes. If value is not set there will be no Text criteria.
|MatchType|enum|Specifies Text matching logic.
|DocumentPageNumber|int|Specifies document-sheet page number to search Barcode Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|SearchAllPages|bool|The flag to search all pages in document
|OptionsType|string|The class name of options object, should always contains value "ImagesSearchBarcodeOptionsData". This property is set automatically when using SDK classes.

## PdfSearchBarcodeOptionsData object

Provides options to search Barcode Signature in Pdf Documents.

Example PdfSearchBarcodeOptionsData object

```javascript
{
  "BarcodeTypeName": "Code128",
  "Text": "John Smith",
  "MatchType": "Contains",
  "DocumentPageNumber": 1,
  "PagesSetup": {
    "FirstPage": false,
    "LastPage": true,
    "OddPages": false,
    "EvenPages": true,
    "PageNumbers": [
      1,
      3,
      5
    ]
  },
  "SearchAllPages": true,
  "OptionsType": "PdfSearchBarcodeOptionsData"
}
```

 PdfSearchBarcodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|BarcodeTypeName|string|Optional Barcode Type name (value one of supported Barcode Type names) to search Barcodes with exact Type. When value is not set no Type criteria.
|Text|string|Optional. Specifies text to search in Barcodes. If value is not set there will be no Text criteria.
|MatchType|enum|Specifies Text matching logic.
|DocumentPageNumber|int|Specifies document-sheet page number to search Barcode Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|SearchAllPages|bool|The flag to search all pages in document
|OptionsType|string|The class name of options object, should always contains value "PdfSearchBarcodeOptionsData". This property is set automatically when using SDK classes.

## SlidesSearchBarcodeOptionsData Object

Provides options to search Barcode Signature in Slides Documents.

Example SlidesSearchBarcodeOptionsData object

```javascript
{
  "BarcodeTypeName": "Code128",
  "Text": "John Smith",
  "MatchType": "Contains",
  "DocumentPageNumber": 1,
  "PagesSetup": {
    "FirstPage": false,
    "LastPage": true,
    "OddPages": false,
    "EvenPages": true,
    "PageNumbers": [
      1,
      3,
      5
    ]
  },
  "SearchAllPages": true,
  "OptionsType": "SlidesSearchBarcodeOptionsData"
}
```

 SlidesSearchBarcodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|BarcodeTypeName|string|Optional Barcode Type name (value one of supported Barcode Type names) to search Barcodes with exact Type. When value is not set no Type criteria.
|Text|string|Optional. Specifies text to search in Barcodes. If value is not set there will be no Text criteria.
|MatchType|enum|Specifies Text matching logic.
|DocumentPageNumber|int|Specifies document-sheet page number to search Barcode Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|SearchAllPages|bool|The flag to search all pages in document
|OptionsType|string|The class name of options object, should always contains value "SlidesSearchBarcodeOptionsData". This property is set automatically when using SDK classes.

## WordsSearchBarcodeOptionsData Object

Provides optionsto search Barcode Signature in Words Documents.

Example WordsSearchBarcodeOptionsData object

```javascript
{
  "BarcodeTypeName": "Code128",
  "Text": "John Smith",
  "MatchType": "Contains",
  "DocumentPageNumber": 1,
  "PagesSetup": {
    "FirstPage": false,
    "LastPage": true,
    "OddPages": false,
    "EvenPages": true,
    "PageNumbers": [
      1,
      3,
      5
    ]
  },
  "SearchAllPages": true,
  "OptionsType": "WordsSearchBarcodeOptionsData"
}
```

 WordsSearchBarcodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|BarcodeTypeName|string|Optional Barcode Type name (value one of supported Barcode Type names) to search Barcodes with exact Type. When value is not set no Type criteria.
|Text|string|Optional. Specifies text to search in Barcodes. If value is not set there will be no Text criteria.
|MatchType|enum|Specifies Text matching logic.
|DocumentPageNumber|int|Specifies document-sheet page number to search Barcode Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|SearchAllPages|bool|The flag to search all pages in document
|OptionsType|string|The class name of options object, should always contains value "WordsSearchBarcodeOptionsData". This property is set automatically when using SDK classes.

## CellsSearchDigitalOptionsData Object

Provides options to search Digital Signature in Cells Documents.

Example CellsSearchDigitalOptionsData object

```javascript
{
  "DocumentPageNumber": 1,
  "SearchAllPages": true,
  "OptionsType": "CellsSearchDigitalOptionsData"
}
```

 CellsSearchDigitalOptionsData Object Fields

|Name|Type|Description
|---|---|---
|DocumentPageNumber|int|Specifies document-sheet page number to search Digital Signature. Parameter is optional. if value is not set program will try to search on any page
|SearchAllPages|bool|The flag to search for Signatures entire all pages in document
|OptionsType|string|The class name of options object, should always contains value "CellsSearchDigitalOptionsData". This property is set automatically when using SDK classes.

## PdfSearchDigitalOptionsData Object

Provides options to search Digital Signature in Pdf Documents.

Example PdfSearchDigitalOptionsData object

```javascript
{
  "DocumentPageNumber": 1,
  "SearchAllPages": true,
  "OptionsType": "PdfSearchDigitalOptionsData"
}
```

 PdfSearchDigitalOptionsData Object Fields

|Name|Type|Description
|---|---|---
|DocumentPageNumber|int|Specifies document-sheet page number to search Digital Signature. Parameter is optional. if value is not set program will try to search on any page
|SearchAllPages|bool|The flag to search for Signatures entire all pages in document
|OptionsType|string|The class name of options object, should always contains value "PdfSearchDigitalOptionsData". This property is set automatically when using SDK classes.

## WordsSearchDigitalOptionsData Object

Provides options to search Digital Signature in Words Documents.

Example WordsSearchDigitalOptionsData object

```javascript
{
  "DocumentPageNumber": 1,
  "SearchAllPages": true,
  "OptionsType": "WordsSearchDigitalOptionsData"
}
```

 WordsSearchDigitalOptionsData Object Fields

|Name|Type|Description
|---|---|---
|DocumentPageNumber|int|Specifies document-sheet page number to search Digital Signature. Parameter is optional. if value is not set program will try to search on any page
|SearchAllPages|bool|The flag to search for Signatures entire all pages in document
|OptionsType|string|The class name of options object, should always contains value "WordsSearchDigitalOptionsData". This property is set automatically when using SDK classes.

## CellsSearchQRCodeOptionsData Object

Provides options to search QRCodeSignature in Cells Documents.

Example CellsSearchQRCodeOptionsData object

```javascript
{
  "QRCodeTypeName": "QR",
  "Text": "John Smith",
  "MatchType": "Contains",
  "DocumentPageNumber": 1,
  "PagesSetup": {
    "FirstPage": false,
    "LastPage": true,
    "OddPages": false,
    "EvenPages": true,
    "PageNumbers": [
      1,
      3,
      5
    ]
  },
  "SearchAllPages": true,
  "OptionsType": "CellsSearchQRCodeOptionsData"
}
```

 CellsSearchQRCodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|QRCodeTypeName|string|Optional QR-Code Type name (value one of supported QR-Code Type names) to search QR-Codes with exact Type. When value is not set no Type criteria.
|Text|string|Optional. Specifies text to search in QR-Codes. If value is not set there will be no Text criteria for Search.
|MatchType|enum|Specifies Text matching logic.
|DocumentPageNumber|int|Specifies document-sheet page number to search Barcode Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|SearchAllPages|bool|The flag to search Signatures entire all pages in Document.
|OptionsType|string|The class name of options object, should always contains value "CellsSearchQRCodeOptionsData". This property is set automatically when using SDK classes.

## ImagesSearchQRCodeOptionsData Object

Provides options to search QRCodeSignature in Images Documents.

Example ImagesSearchQRCodeOptionsData object

```javascript
{
  "qrCodeTypeName": "Aztec",
  "text": "John Smith",
  "matchType": "Contains",
  "documentPageNumber": 3,
  "pagesSetup": {
    "firstPage": false,
    "lastPage": true,
    "oddPages": false,
    "evenPages": true,
    "pageNumbers": [
      1,
      3,
      5
    ]
  },
  "searchAllPages": true,
  "optionsType": "ImagesSearchQRCodeOptionsData"
}
```

 ImagesSearchQRCodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|QRCodeTypeName|string|Optional QR-Code Type name (value one of supported QR-Code Type names) to search QR-Codes with exact Type. When value is not set no Type criteria.
|Text|string|Optional. Specifies text to search in QR-Codes. If value is not set there will be no Text criteria for Search.
|MatchType|enum|Specifies Text matching logic.
|DocumentPageNumber|int|Specifies document-sheet page number to search Barcode Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|SearchAllPages|bool|The flag to search Signatures entire all pages in Document.
|OptionsType|string|The class name of options object, should always contains value "ImagesSearchQRCodeOptionsData". This property is set automatically when using SDK classes.

## PdfSearchQRCodeOptionsData Object

Provides options to search QRCode Signature in Pdf Documents.

Example PdfSearchQRCodeOptionsData object

```javascript
{
  "QRCodeTypeName": "QR",
  "Text": "John Smith",
  "MatchType": "Contains",
  "DocumentPageNumber": 1,
  "PagesSetup": {
    "FirstPage": false,
    "LastPage": true,
    "OddPages": false,
    "EvenPages": true,
    "PageNumbers": [
      1,
      3,
      5
    ]
  },
  "SearchAllPages": true,
  "OptionsType": "PdfSearchQRCodeOptionsData"
}
```

 PdfSearchQRCodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|QRCodeTypeName|string|Optional QR-Code Type name (value one of supported QR-Code Type names) to search QR-Codes with exact Type. When value is not set no Type criteria.
|Text|string|Optional. Specifies text to search in QR-Codes. If value is not set there will be no Text criteria for Search.
|MatchType|enum|Specifies Text matching logic.
|DocumentPageNumber|int|Specifies document-sheet page number to search Barcode Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|SearchAllPages|bool|The flag to search Signatures entire all pages in Document.
|OptionsType|string|The class name of options object, should always contains value "PdfSearchQRCodeOptionsData". This property is set automatically when using SDK classes.

## SlidesSearchQRCodeOptionsData Object

Provides options to search QRCodeSignature in Slides Documents.

Example SlidesSearchQRCodeOptionsData object

```javascript
{
  "QRCodeTypeName": "QR",
  "Text": "John Smith",
  "MatchType": "Contains",
  "DocumentPageNumber": 1,
  "PagesSetup": {
    "FirstPage": false,
    "LastPage": true,
    "OddPages": false,
    "EvenPages": true,
    "PageNumbers": [
      1,
      3,
      5
    ]
  },
  "SearchAllPages": true,
  "OptionsType": "SlidesSearchQRCodeOptionsData"
}
```

 SlidesSearchQRCodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|QRCodeTypeName|string|Optional QR-Code Type name (value one of supported QR-Code Type names) to search QR-Codes with exact Type. When value is not set no Type criteria.
|Text|string|Optional. Specifies text to search in QR-Codes. If value is not set there will be no Text criteria for Search.
|MatchType|enum|Specifies Text matching logic.
|DocumentPageNumber|int|Specifies document-sheet page number to search Barcode Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|SearchAllPages|bool|The flag to search Signatures entire all pages in Document.
|OptionsType|string|The class name of options object, should always contains value "SlidesSearchQRCodeOptionsData". This property is set automatically when using SDK classes.

## WordsSearchQRCodeOptionsData Object

Provides options to search QR-Code Signature in Words Documents.

Example WordsSearchQRCodeOptionsData object

```javascript

{
  "QRCodeTypeName": "QR",
  "Text": "John Smith",
  "MatchType": "Contains",
  "DocumentPageNumber": 1,
  "PagesSetup": {
    "FirstPage": false,
    "LastPage": true,
    "OddPages": false,
    "EvenPages": true,
    "PageNumbers": [
      1,
      3,
      5
    ]
  },
  "SearchAllPages": true,
  "OptionsType": "WordsSearchQRCodeOptionsData"
}

```

 WordsSearchQRCodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|QRCodeTypeName|string|Optional QR-Code Type name (value one of supported QR-Code Type names) to search QR-Codes with exact Type. When value is not set no Type criteria.
|Text|string|Optional. Specifies text to search in QR-Codes. If value is not set there will be no Text criteria for Search.
|MatchType|enum|Specifies Text matching logic.
|DocumentPageNumber|int|Specifies document-sheet page number to search Barcode Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|SearchAllPages|bool|The flag to search Signatures entire all pages in Document.
|OptionsType|string|The class name of options object, should always contains value "WordsSearchQRCodeOptionsData". This property is set automatically when using SDK classes.
