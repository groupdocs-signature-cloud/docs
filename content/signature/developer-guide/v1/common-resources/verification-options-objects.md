---
id: "verification-options-objects"
url: "signature/verification-options-objects"
title: "Verification Options Objects"
productName: "GroupDocs.Signature Cloud"
weight: 2
description: ""
keywords: ""
---

{{< alert style="info" >}}
Note:  The features listed in this page are supported only in GroupDocs.Signature Cloud V1
{{< /alert >}}

Page contains description for Verification Options objects and object properties

## VerifyOptionsCollectionData Object

Provides list of options for documents verification.

Example VerifyOptionsCollectionData object

```javascript
{
  "items": [
    {
  "items": [
    {
      "barcodeTypeName": "Code39Standard",
      "matchType": "Contains",
      "text": "123456789012",
      "verifyAllPages": true,
      "isValid": false,
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
    },
    {
      "password": "1234567890",
      "certificateGuid": "certificates\SherlockHolmes.pfx",
      "isValid": false,
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
    }
  ]
}
```

 VerifyOptionsCollectionData Object Fields

|Name|Type|Description
|---|---|---
|Items|List<VerifyOptionsData>|List of Verify Options records.

## CellsVerifyTextOptionsData Object

Provides options to verify Text Signature in Cells Documents.

Example CellsVerifyTextOptionsData object

```javascript
{
  "DocumentPageNumber": 1,
  "Text": "John Smith",
  "VerifyAllPages" : true,
  "OptionsType": "CellsVerifyTextOptionsData"
 }
```

 CellsVerifyTextOptionsData Object Fields

|Name|Type|Description
|---|---|---
|Text|string|Text of Signature to verify. Default value is empty.
|DocumentPageNumber|int|Specifies document-sheet page number to verify Text Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|VerifyAllPages|bool|The flag to verify all pages in document
|OptionsType|string|The class name of options object, should always contains value "CellsVerifyTextOptionsData". This property is set automatically when using SDK classes.

## PdfVerifyTextOptionsData ##

Provides options to verify Text Signature in Pdf Documents.

Example PdfVerifyTextOptionsData object

```javascript
{
  "SignatureID" : 1001,
  "SignatureImplementation" : "Stamp",
  "DocumentPageNumber": 1,
  "Text": "John Smith",
  "VerifyAllPages" : true,
  "OptionsType": "PdfVerifyTextOptionsData"
 }
```

 PdfVerifyTextOptions Object Fields

|Name|Type|Description
|---|---|---
|SignatureID|int|unique identifier of Text Signature for Stamp Text signature implementation
|SignatureImplementation|enum|Specifies type of Signature implementation to verify
|Text|string|Text of Signature. Default value is empty.
|DocumentPageNumber|int|Specifies document-sheet page number to verify Text Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|VerifyAllPages|bool|The flag to verify all pages in document
|OptionsType|string|The class name of options object, should always contains value "PdfVerifyTextOptionsData". This property is set automatically when using SDK classes.

## SlidesVerifyTextOptionsData Object

Provides options to verify Text Signature in Slides Documents.

Example SlidesVerifyTextOptionsData object

```javascript
{
  "DocumentPageNumber": 1,
  "Text": "John Smith",
  "VerifyAllPages" : true,
  "OptionsType": "SlidesVerifyTextOptionsData"
 }
```

 SlidesVerifyTextOptionsData Object Fields

|Name|Type|Description
|---|---|---
|Text|string|Text of Signature. Default value is empty.
|DocumentPageNumber|int|Specifies document-sheet page number to verify Text Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|VerifyAllPages|bool|The flag to verify all pages in document
|OptionsType|string|The class name of options object, should always contains value "SlidesVerifyTextOptionsData". This property is set automatically when using SDK classes.

## WordsVerifyTextOptionsData Object

Provides optionsto verify Text Signature in Words Documents.

Example WordsVerifyTextOptionsData object

```javascript
{
  "DocumentPageNumber": 1,
  "Text": "John Smith",
  "VerifyAllPages" : true,
  "OptionsType": "WordsVerifyTextOptionsData"
 }
```

 WordsVerifyTextOptionsData Object Fields

|Name|Type|Description
|---|---|---
|Text|string|Text of Signature to verify
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|SheetNumber|int|Specifies document-sheet page number to add Text Signature.
|OptionsType|string|The class name of options object, should always contains value "WordsVerifyTextOptionsData". This property is set automatically when using SDK classes.

## CellsVerifyDigitalOptionsData Object

Provides options to verify Digital Signature in Cells Documents.

Example CellsVerifyDigitalOptionsData object

```javascript
{
  "DocumentPageNumber": 1,
  "Password" : "1234567890",
  "CertificateGuid": "mrjohn.smith.crt",
  "Comments" : "verified data",
  "SignDateTimeFrom" : "1/12/2017",
  "SignDateTimeTo" : "12/12/2017",
  "OptionsType": "CellsVerifyDigitalOptionsData"
 }
```

 CellsVerifyTextOptionsData Object Fields

|Name|Type|Description
|---|---|---
|Text|string|Text of Signature to verify. Default value is empty.
|DocumentPageNumber|int|Specifies document-sheet page number to verify Text Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|VerifyAllPages|bool|The flag to verify all pages in document
|OptionsType|string|The class name of options object, should always contains value "CellsVerifyDigitalOptionsData". This property is set automatically when using SDK classes.

## PdfVerifyDigitalOptionsData object

Provides options to verify Digital Signature in Pdf Documents.

Example PdfVerifyDigitalOptionsData object

```javascript
{
  "DocumentPageNumber": 1,
  "Password" : "1234567890",
  "CertificateGuid": "mrjohn.smith.crt",
  "Reason" : "reason",
  "Contact" : "mrJohn",
  "Location" : "Storage",
  "OptionsType": "PdfVerifyDigitalOptionsData"
 }
```

 PdfVerifyDigitalOptionsData Object Fields

|Name|Type|Description
|---|---|---
|SignatureID|int|unique identifier of Text Signature for Stamp Text signature implementation
|SignatureImplementation|enum|Specifies type of Signature implementation to verify
|Text|string|Text of Signature. Default value is empty.
|DocumentPageNumber|int|Specifies document-sheet page number to verify Text Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|VerifyAllPages|bool|The flag to verify all pages in document
|OptionsType|string|The class name of options object, should always contains value "PdfVerifyDigitalOptionsData". This property is set automatically when using SDK classes.

## WordsVerifyDigialOptionsData Object

Provides options to verify Digital Signature in Words Documents.

Example WordsVerifyDigitalOptionsData object

```javascript
{
  "DocumentPageNumber": 1,
  "Password" : "1234567890",
  "CertificateGuid": "mrjohn.smith.crt",
  "Comments" : "verified data",
  "SignDateTimeFrom" : "1/12/2017",
  "SignDateTimeTo" : "12/12/2017",
  "OptionsType": "WordsVerifyDigitalOptionsData"
 }
```

 WordsVerifyTextOptionsData Object Fields

|Name|Type|Description
|---|---|---
|Text|string|Text of Signature to verify
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|SheetNumber|int|Specifies document-sheet page number to add Text Signature.
|OptionsType|string|The class name of options object, should always contains value "WordsVerifyDigitalOptionsData". This property is set automatically when using SDK classes.

## CellsVerifyBarcodeOptionsData Object

Provides options to verify Barcode Signature in Cells Documents.

Example CellsVerifyBarcodeOptionsData object

```javascript
{
  "BarcodeTypeName" : "Code128",
  "MatchType" : "Exact",
  "DocumentPageNumber": 1,
  "Text": "John Smith",
  "VerifyAllPages" : true,
  "OptionsType": "CellsVerifyBarcodeOptionsData"
 }
```

 CellsVerifyTextOptionsData Object Fields

|Name|Type|Description
|---|---|---
|BarcodeTypeName|string|Barcode encode type name to verify on document page(s). List of supported Barcode encode type names could be found in Barcode Resources
|MatchType|enum|Specifies Text matching logic.
|Text|string|Text of Signature to verify. Default value is empty.
|DocumentPageNumber|int|Specifies document-sheet page number to verify Text Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|VerifyAllPages|bool|The flag to verify all pages in document
|OptionsType|string|The class name of options object, should always contains value "CellsVerifyBarcodeOptionsData". This property is set automatically when using SDK classes.

## ImagesVerifyBarcodeOptionsData Object

Provides options to verify Barcode Signature in Images Documents.

Example ImagesVerifyBarcodeOptionsData object

```javascript
{
  "barcodeTypeName": "Code39Standard",
  "matchType": "Contains",
  "text": "123456789012",
  "verifyAllPages": true,
  "isValid": false,
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
  "optionsType": "ImagesVerifyBarcodeOptionsData"
}
```

 CellsVerifyTextOptionsData Object Fields

|Name|Type|Description
|---|---|---
|BarcodeTypeName|string|Barcode encode type name to verify on document page(s). List of supported Barcode encode type names could be found in Barcode Resources
|Text|string|Optional. Specifies text to search in Barcodes. If value is not set there will be no Text criteria.
|MatchType|enum|Specifies Text matching logic.
|DocumentPageNumber|int|Specifies document-sheet page number to verify Text Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|VerifyAllPages|bool|The flag to verify all pages in document
|OptionsType|string|The class name of options object, should always contains value "CellsVerifyBarcodeOptionsData". This property is set automatically when using SDK classes.

## PdfVerifyBarcodeOptionsData object

Provides options to verify Barcode Signature in Pdf Documents.

Example PdfVerifyBarcodeOptionsData object

```javascript
{
  "BarcodeTypeName" : "Code128",
  "MatchType" : "Exact",
  "DocumentPageNumber": 1,
  "Text": "John Smith",
  "VerifyAllPages" : true,
  "OptionsType": "PdfVerifyBarcodeOptionsData"
 }
```

 PdfVerifyBarcodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|BarcodeTypeName|string|Barcode encode type name to verify on document page(s). List of supported Barcode encode type names could be found in Barcode Resources
|MatchType|enum|Specifies enumeration of possible Barcode Text match - Exact match, Starts With, Ends With, Contains
|Text|string|Text of Signature. Default value is empty.
|DocumentPageNumber|int|Specifies document-sheet page number to verify Text Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|VerifyAllPages|bool|The flag to verify all pages in document
|OptionsType|string|The class name of options object, should always contains value "PdfVerifyBarcodeOptionsData". This property is set automatically when using SDK classes.

## SlidesVerifyBarcodeOptionsData Object

Provides options to verify Barcode Signature in Slides Documents.

Example SlidesVerifyBarcodeOptionsData object

```javascript
{
  "BarcodeTypeName" : "Code128",
  "MatchType" : "Exact",
  "DocumentPageNumber": 1,
  "Text": "John Smith",
  "VerifyAllPages" : true,
  "OptionsType": "SlidesVerifyBarcodeOptionsData"
 }
```

 SlidesVerifyBarodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|BarcodeTypeName|string|Barcode encode type name to verify on document page(s). List of supported Barcode encode type names could be found in Barcode Resources
|MatchType|enum|Specifies enumeration of possible Barcode Text match - Exact match, Starts With, Ends With, Contains
|Text|string|Text of Signature. Default value is empty.
|DocumentPageNumber|int|Specifies document-sheet page number to verify Text Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|VerifyAllPages|bool|The flag to verify all pages in document
|OptionsType|string|The class name of options object, should always contains value "SlidesVerifyBarcodeOptionsData". This property is set automatically when using SDK classes.

## WordsVerifyBarcodeOptionsData Object

Provides options to verify Barcode Signature in Words Documents.

Example WordsVerifyBarcodeOptionsData object

```javascript

{
  "BarcodeTypeName" : "Code128",
  "MatchType" : "Exact",
  "DocumentPageNumber": 1,
  "Text": "John Smith",
  "VerifyAllPages" : true,
  "OptionsType": "WordsVerifyBarcodeOptionsData"
 }

```

|Name|Type|Description
|---|---|---
|BarcodeTypeName|string|Barcode encode type name to verify on document page(s). List of supported Barcode encode type names could be found in Barcode Resources
|MatchType|enum|Specifies enumeration of possible Barcode Text match - Exact match, Starts With, Ends With, Contains
|Text|string|Text of Signature to verify
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|SheetNumber|int|Specifies document-sheet page number to add Text Signature.
|OptionsType|string|The class name of options object, should always contains value "WordsVerifyBarcodeOptionsData". This property is set automatically when using SDK classes.

## CellsVerifyQRCodeOptionsData Object

Provides options to verify QRCodeSignature in Cells Documents.

Example CellsVerifyQRCodeOptionsData object

```javascript
{
  "QRCodeTypeName" : "QRCode",
  "MatchType" : "Exact",
  "DocumentPageNumber": 1,
  "Text": "John Smith",
  "VerifyAllPages" : true,
  "OptionsType": "CellsVerifyQRCodeOptionsData"
 }
```

 CellsVerifyQRCodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|QRCodeTypeName|string|QR-Code encode type name to verify on document page(s). List of supported QR-Code encode type names could be found in QR-Code Resources
|MatchType|enum|Specifies enumeration of possible QR-Code Text match - Exact match, Starts With, Ends With, Contains
|Text|string|Text of QR-Code Signature to verify. Default value is empty.
|DocumentPageNumber|int|Specifies document-sheet page number to verify QR-Code Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|VerifyAllPages|bool|The flag to verify all pages in document
|OptionsType|string|The class name of options object, should always contains value "CellsVerifyQRCodeOptionsData". This property is set automatically when using SDK classes.

## ImagesVerifyQRCodeOptionsData Object

Provides options to verify QRCodeSignature in Images Documents.

Example ImagesVerifyQRCodeOptionsData object

```javascript
{
  "qrCodeTypeName": "Aztec",
  "matchType": "Contains",
  "text": "John Smith",
  "verifyAllPages": true,
  "isValid": false,
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
  "optionsType": "ImagesVerifyQRCodeOptionsData"
}
```

 ImagesVerifyQRCodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|QRCodeTypeName|string|QR-Code encode type name to verify on document page(s). List of supported QR-Code encode type names could be found in QR-Code Resources
|MatchType|enum|Specifies Text matching logic.
|Text|string|Text of QR-Code Signature to verify. Default value is empty.
|DocumentPageNumber|int|Specifies document-sheet page number to verify QR-Code Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|VerifyAllPages|bool|The flag to verify all pages in document
|OptionsType|string|The class name of options object, should always contains value "ImagesVerifyQRCodeOptionsData". This property is set automatically when using SDK classes.

## PdfVerifyQRCodeOptionsData object

Provides options to verify QRCode Signature in Pdf Documents.

Example PdfVerifyQRCodeOptionsData object

```javascript
{
  "QRCodeTypeName" : "QRCode",
  "MatchType" : "Exact",
  "DocumentPageNumber": 1,
  "Text": "John Smith",
  "VerifyAllPages" : true,
  "OptionsType": "PdfVerifyQRCodeOptionsData"
 }
```

 PdfVerifyQRCodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|QRCodeTypeName|string|QR-Code encode type name to verify on document page(s). List of supported QR-Code encode type names could be found in QR-Code Resources
|MatchType|enum|Specifies enumeration of possible QR-Code Text match - Exact match, Starts With, Ends With, Contains
|Text|string|Text of QR-Code Signature to verify. Default value is empty.
|DocumentPageNumber|int|Specifies document-sheet page number to verify QR-Code Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|VerifyAllPages|bool|The flag to verify all pages in document
|OptionsType|string|The class name of options object, should always contains value "PdfVerifyQRCodeOptionsData". This property is set automatically when using SDK classes.

## SlidesVerifyQRCodeOptionsData Object

Provides options to verify QRCodeSignature in Slides Documents.

Example SlidesVerifyQRCodeOptionsData object

```javascript
{
  "BarcodeTypeName" : "Code128",
  "MatchType" : "Exact",
  "DocumentPageNumber": 1,
  "Text": "John Smith",
  "VerifyAllPages" : true,
  "OptionsType": "SlidesVerifyQRCodeOptionsData"
 }
```

 SlidesVerifyQRCodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|QRCodeTypeName|string|QR-Code encode type name to verify on document page(s). List of supported QR-Code encode type names could be found in QR-Code Resources
|MatchType|enum|Specifies enumeration of possible QR-Code Text match - Exact match, Starts With, Ends With, Contains
|Text|string|Text of QR-Code Signature to verify. Default value is empty.
|DocumentPageNumber|int|Specifies document-sheet page number to verify QR-Code Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|VerifyAllPages|bool|The flag to verify all pages in document
|OptionsType|string|The class name of options object, should always contains value "SlidesVerifyQRCodeOptionsData". This property is set automatically when using SDK classes.

## WordsVerifyQRCodeOptionsData Object

Provides options to verify QR-Code Signature in Words Documents.

Example WordsVerifyQRCodeOptionsData object

```javascript

{
  "QRCodeTypeName" : "QRCode",
  "MatchType" : "Exact",
  "DocumentPageNumber": 1,
  "Text": "John Smith",
  "VerifyAllPages" : true,
  "OptionsType": "WordsVerifyQRCodeOptionsData"
 }

```

|Name|Type|Description
|---|---|---
|QRCodeTypeName|string|QR-Code encode type name to verify on document page(s). List of supported QR-Code encode type names could be found in QR-Code Resources
|MatchType|enum|Specifies enumeration of possible QR-Code Text match - Exact match, Starts With, Ends With, Contains
|Text|string|Text of QR-Code Signature to verify. Default value is empty.
|DocumentPageNumber|int|Specifies document-sheet page number to verify QR-Code Signature. Parameter is optional. if value is not set program will try to find on any page
|PagesSetup|struct|Specifies Page Setting to define separate pages to process.
|VerifyAllPages|bool|The flag to verify all pages in document
|OptionsType|string|The class name of options object, should always contains value "WordsVerifyQRCodeOptionsData". This property is set automatically when using SDK classes.
