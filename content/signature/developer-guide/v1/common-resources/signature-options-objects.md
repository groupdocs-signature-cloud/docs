---
id: "signature-options-objects"
url: "signature/signature-options-objects"
title: "Signature Options Objects"
productName: "GroupDocs.Signature Cloud"
weight: 1
description: ""
keywords: ""
toc: True
---

{{< alert style="info" >}}
Note:  The features listed in this page are supported only in GroupDocs.Signature Cloud V1
{{< /alert >}}

Page contains description for Signature Options objects and object properties

## SignOptionsCollectionData Object

Provides list of options for documents signing.

Example SignOptionsCollectionData object

```javascript
{
  "items": [
    {
      "barcodeTypeName": "Code39Standard",
      "borderVisiblity": true,
      "borderDashStyle": "Solid",
      "borderWeight": 1.0,
      "opacity": 1.0,
      "text": "123456789012",
      "left": 10,
      "top": 10,
      "width": 200,
      "height": 100,
      "locationMeasureType": "Pixels",
      "sizeMeasureType": "Pixels",
      "stretch": "PageHeight",
      "rotationAngle": 0,
      "horizontalAlignment": "Left",
      "verticalAlignment": "Center",
      "margin": {
        "all": 5,
        "left": 5,
        "top": 5,
        "right": 5,
        "bottom": 5
      },
      "marginMeasureType": "Pixels",
      "signAllPages": false,
      "font": {
        "fontFamily": "Times New Roman",
        "fontSize": 14.0,
        "bold": false,
        "italic": false,
        "underline": false
      },
      "foreColor": {
        "Web": "Black"
      },
      "borderColor": {
        "Web": "Transparent",
        "Alpha": 0
      },
      "backgroundColor": {
        "Web": "Transparent",
        "Alpha": 0
      },
      "documentPageNumber": 1,
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
      "certificateGuid": "folder\file.pdf",
      "left": 10,
      "top": 10,
      "width": 200,
      "height": 100,
      "locationMeasureType": "Pixels",
      "sizeMeasureType": "Pixels",
      "rotationAngle": 90,
      "horizontalAlignment": "Left",
      "verticalAlignment": "Center",
      "margin": {
        "all": 5,
        "left": 5,
        "top": 5,
        "right": 5,
        "bottom": 5
      },
      "marginMeasureType": "Pixels",
      "opacity": 0.9,
      "signAllPages": false,
      "documentPageNumber": 1,
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

 SignOptionsCollectionData Object Fields

|Name|Type|Description
|---|---|---
|Items|List<SignOptionsData>|List of Signature Options objects.

## CellsSignTextOptionsData Object

Provides options for Cells Documents to add Text Signature.

Example CellsSignTextOptionsData object

```javascript
{
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "sheetNumber": 1,
  "rowNumber": 2,
  "columnNumber": 2,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "marginMeasureType": "Pixels",
  "borderVisiblity": true,
  "borderDashStyle": "Dash",
  "borderTransparency": 0.55,
  "borderWeight": 12.0,
  "backgroundTransparency": 0.8,
  "signatureImplementation": "TextStamp",
  "text": "John Smith",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 100,
  "stretch": "None",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "signAllPages": false,
  "font": {
    "fontFamily": "Times New Roman",
    "fontSize": 14.0,
    "bold": false,
    "italic": false,
    "underline": false
  },
  "foreColor": {
    "Web": "DarkOrange"
  },
  "borderColor": {
    "Web": "DarkOrange"
  },
  "backgroundColor": {
    "Web": "BlueViolet"
  },
  "documentPageNumber": 1,
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
  "optionsType": "CellsSignTextOptionsData"
}
```

 CellsSignTextOptionsData Object Fields

|Name|Type|Description
|---|---|---
|Text|string|Text of Signature. Default value is empty.
|SignatureImplementation|enum|Specifies Text Signature Implementation Type.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SheetNumber|int|Gets or sets worksheet number for signing. DocumentPageNumber parameter contains the same value.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height. (This property is obsolete.)
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|ColumnNumber|int|Gets or sets the left column number of signature (min value is 0). Left parameter contains the same value.
|RowNumber|int|Gets or sets the top row number of signature (min value is 0).Top parameter contains the same value.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top. (This property is obsolete.)
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin. (This property is obsolete.)
|Font|SignatureFontData|Gets or sets the font of signature.
|ForeColor|Color|Gets or sets the fore color of signature.
|BorderColor|Color|Gets or sets the border color of signature.
|BackgroundColor|Color|Gets or sets the background color of signature.
|Stretch|enum|Specifies stretch mode for Signature. Values are  None, PageWidth, PageHeight, PageArea.
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|BorderVisiblity|bool|Enables Signature border. Default value is true.
|BorderDashStyle|DashStyleData|Gets or sets the signature border style.
|BorderTransparency|float|Specifies Transparency of Text Signature Area Border. Value should be in range 0 - 1. When 0 means no transparency and 1 absolutely transparent object. Default value is 0
|BorderWeight|int|Specifies Border Width of Signature Area
|BackgroundTransparency|float|Specifies Transparency of Text Signature Area Background. Value should be in range 0 - 1. When 0 means no transparency and 1 absolutely transparent object. Default value is 0
|OptionsType|string|The class name of options object, should always contains value "CellsSignTextOptionsData". This property is set automatically when using SDK classes.

## ImagesSignTextOptionsData Object

Provides options for Images Documents to add Text Signature.

Example ImagesSignTextOptionsData object

```javascript
{
  "opacity": 0.9,
  "signatureImplementation": "TextAsImage",
  "borderDashStyle": 0,
  "borderTransparency": 0.0,
  "borderWeight": 1.0,
  "backgroundTransparency": 0.0,
  "text": "John Smith",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 100,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "stretch": "None",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "marginMeasureType": "Pixels",
  "signAllPages": false,
  "font": {
    "fontFamily": "Times New Roman",
    "fontSize": 14.0,
    "bold": false,
    "italic": false,
    "underline": false
  },
  "foreColor": {
    "Web": "DarkOrange"
  },
  "borderColor": {
    "Web": "DarkOrange"
  },
  "backgroundColor": {
    "Web": "BlueViolet"
  },
  "documentPageNumber": 1,
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
  "optionsType": "ImagesSignTextOptionsData"
}
```

 ImagesSignTextOptionsData Object Fields

|Name|Type|Description
|---|---|---
|Text|string|Text of Signature. Default value is empty.
|SignatureImplementation|enum|Specifies Text Signature Implementation Type.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top.
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin.
|Font|SignatureFontData|Gets or sets the font of signature.
|ForeColor|Color|Gets or sets the fore color of signature.
|BorderColor|Color|Gets or sets the border color of signature.
|BackgroundColor|Color|Gets or sets the background color of signature.
|Stretch|enum|Specifies stretch mode for Signature. Values are  None, PageWidth, PageHeight, PageArea.
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Opacity|double|Gets or sets the signature opacity (value from 0.0 (clear) through 1.0 (opaque)). By default the value is 1.0.
|BorderDashStyle|enum|Gets or sets the signature border style.
|BorderTransparency|double|Gets or sets the signature border transparency (value from 0.0 (opaque) through 1.0 (clear)).
|BorderWeight|double|Gets or sets the weight of the signature border.
|BackgroundTransparency|double|Gets or sets the signature background transparency (value from 0.0 (opaque) through 1.0 (clear)).
|OptionsType|string|The class name of options object, should always contains value "ImagesSignTextOptionsData". This property is set automatically when using SDK classes.

## PdfSignTextOptionsData object

Provides options for Pdf Documents to add Text Signature.

Example PdfSignTextOptionsData object

```javascript
{
  "opacity": 0.8,
  "signatureID": 12,
  "signatureImplementation": "Stamp",
  "formTextFieldTitle": "John Smith",
  "formTextFieldType": "PlainText",
  "text": "John Smith",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 100,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "stretch": "None",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "marginMeasureType": "Pixels",
  "signAllPages": false,
  "font": {
    "fontFamily": "Times New Roman",
    "fontSize": 14.0,
    "bold": false,
    "italic": false,
    "underline": false
  },
  "foreColor": {
    "Web": "DarkOrange"
  },
  "borderColor": {
    "Web": "DarkOrange"
  },
  "backgroundColor": {
    "Web": "BlueViolet"
  },
  "documentPageNumber": 1,
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
  "optionsType": "PdfSignTextOptionsData"
}
```

 PdfSignTextOptions Object Fields

|Name|Type|Description
|---|---|---
|Text|string|Text of Signature. Default value is empty. 
|SignatureImplementation|enum|Specifies Text Signature Implementation Type.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top.
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin.
|Font|SignatureFontData|Gets or sets the font of signature.
|ForeColor|Color|Gets or sets the fore color of signature.
|BorderColor|Color|Gets or sets the border color of signature.
|BackgroundColor|Color|Gets or sets the background color of signature.
|Stretch|enum|Specifies stretch mode for Signature. Values are  None, PageWidth, PageHeight, PageArea.
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|SignatureID|int|Gets or sets the unique ID of signature. It can be used in signature verification options.
|FormTextFieldTitle|string|Gets or sets the title of text form field to put text signature into it. This property could be used only with PdfTextSignatureImplementation # TextToFormField.
|FormTextFieldType|enum|Gets or sets the type of form field to put text signature into it. This property could be used only with PdfTextSignatureImplementation # TextToFormField. Value by default is AllTextTypes.
|OptionsType|string|The class name of options object, should always contains value "PdfSignTextOptionsData ". This property is set automatically when using SDK classes.

## SlidesSignTextOptionsData Object

Provides options to put Text Signature on Slides Documents.

Example SlidesSignTextOptionsData object

```javascript
{
  "borderTransparency": 0.55,
  "borderWeight": 12.0,
  "backgroundTransparency": 0.8,
  "signatureImplementation": "TextStamp",
  "text": "John Smith",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 100,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "stretch": "None",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "marginMeasureType": "Pixels",
  "signAllPages": false,
  "font": {
    "fontFamily": "Times New Roman",
    "fontSize": 14.0,
    "bold": false,
    "italic": false,
    "underline": false
  },
  "foreColor": {
    "Web": "DarkOrange"
  },
  "borderColor": {
    "Web": "DarkOrange"
  },
  "backgroundColor": {
    "Web": "BlueViolet"
  },
  "documentPageNumber": 1,
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
  "optionsType": "SlidesSignTextOptionsData"
}
```

 SlidesSignTextOptionsData Object Fields

|Name|Type|Description
|---|---|---
|Text|string|Text of Signature. Default value is empty.
|SignatureImplementation|enum|Specifies Text Signature Implementation Type.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top.
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin.
|Font|SignatureFontData|Gets or sets the font of signature.
|ForeColor|Color|Gets or sets the fore color of signature.
|BorderColor|Color|Gets or sets the border color of signature.
|BackgroundColor|Color|Gets or sets the background color of signature.
|BorderTransparency|double|Gets or sets the signature border transparency (value from 0.0 (opaque) through 1.0 (clear)).
|BorderWeight|double|Gets or sets the weight of the signature border.
|BackgroundTransparency|double|Gets or sets the signature background transparency (value from 0.0 (opaque) through 1.0 (clear)).
|Stretch|enum|Specifies stretch mode for Signature. Values are  None, PageWidth, PageHeight, PageArea.
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|OptionsType|string|The class name of options object, should always contains value "ImagesSignTextOptionsData". This property is set automatically when using SDK classes.

## WordsSignTextOptionsData Object

Provides options for Text Signature object for Words Documents.

Example WordsSignTextOptionsData object

```javascript
{
  "borderDashStyle": 5,
  "borderTransparency": 0.55,
  "borderWeight": 12.0,
  "backgroundTransparency": 0.8,
  "signatureImplementation": "TextStamp",
  "text": "John Smith",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 100,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "stretch": "None",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "marginMeasureType": "Pixels",
  "signAllPages": false,
  "font": {
    "fontFamily": "Times New Roman",
    "fontSize": 14.0,
    "bold": false,
    "italic": false,
    "underline": false
  },
  "foreColor": {
    "Web": "DarkOrange"
  },
  "borderColor": {
    "Web": "DarkOrange"
  },
  "backgroundColor": {
    "Web": "BlueViolet"
  },
  "documentPageNumber": 1,
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
  "optionsType": "WordsSignTextOptionsData"
}
```

 WordsSignTextOptionsData Object Fields

|Name|Type|Description
|---|---|---
|Text|string|Text of Signature. Default value is empty.
|SignatureImplementation|enum|Specifies Text Signature Implementation Type.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top.
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin.
|Font|SignatureFontData|Gets or sets the font of signature.
|BorderDashStyle|enum|Gets or sets the signature border style.
|ForeColor|Color|Gets or sets the fore color of signature.
|BorderColor|Color|Gets or sets the border color of signature.
|BackgroundColor|Color|Gets or sets the background color of signature.
|BorderTransparency|double|Gets or sets the signature border transparency (value from 0.0 (opaque) through 1.0 (clear)).
|BorderWeight|double|Gets or sets the weight of the signature border.
|BackgroundTransparency|double|Gets or sets the signature background transparency (value from 0.0 (opaque) through 1.0 (clear)).
|Stretch|enum|Specifies stretch mode for Signature. Values are  None, PageWidth, PageHeight, PageArea.
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|OptionsType|string|The class name of options object, should always contains value "WordsSignTextOptionsData". This property is set automatically when using SDK classes.

## CellsSignImageOptionsData Object

Provides options to put Image Signature on Cells Documents Pages.

Example CellsSignImageOptionsData object

```javascript
{
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "sheetNumber": 1,
  "rowNumber": 2,
  "columnNumber": 2,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "marginMeasureType": "Pixels",
  "imageGuid": "images\signature_01.jpg",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 100,
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "opacity": 0.9,
  "signAllPages": false,
  "documentPageNumber": 1,
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
  "optionsType": "CellsSignImageOptionsData"
}
```

 CellsSignImageOptionsData Object Fields

|Name|Type|Description
|---|---|---
|ImageGuid|string|Gets or sets the signature image file name.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SheetNumber|int|Gets or sets worksheet number for signing. DocumentPageNumber parameter contains the same value.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height. (This property is obsolete.)
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|RowNumber|int|Gets or sets the top row number of signature (min value is 0). Top parameter contains the same value.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|ColumnNumber|int|Gets or sets the left column number of signature (min value is 0). Left parameter contains the same value.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top. (This property is obsolete.)
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin. (This property is obsolete.)
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Opacity|double|Gets or sets the additional opacity for sign image (value from 0.0 (clear) through 1.0 (opaque)). By default the value is 1.0.
|OptionsType|string|The class name of options object, should always contains value "CellsSignImageOptionsData". This property is set automatically when using SDK classes.

## ImagesSignImageOptionsData Object

Provides options for Images Documents to add Image Signature.

Example ImagesSignImageOptionsData object.

```javascript
{
  "imageGuid": "images\signature_01.jpg",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 100,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "marginMeasureType": "Pixels",
  "opacity": 0.9,
  "signAllPages": false,
  "documentPageNumber": 1,
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
  "optionsType": "ImagesSignImageOptionsData"
}
```

 ImagesSignImageOptionsData Object Fields

|Name|Type|Description
|---|---|---
|ImageGuid|string|Gets or sets the signature image file name.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top.
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin.
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Opacity|double|Gets or sets the signature opacity (value from 0.0 (clear) through 1.0 (opaque)).
|OptionsType|string|The class name of options object, should always contains value "ImagesSignImageOptionsData". This property is set automatically when using SDK classes.

## PdfSignImageOptionsData Object

Provides options to add Image Signature on Document pages.

Example PdfSignImageOptionsData object

```javascript

{
  "imageGuid": "images\signature_01.jpg",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 100,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "marginMeasureType": "Pixels",
  "opacity": 0.9,
  "signAllPages": false,
  "documentPageNumber": 1,
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
  "optionsType": "PdfSignImageOptionsData"
}

```

 PdfSignImageOptionsData Object Fields

|Name|Type|Description
|---|---|---
|ImageGuid|string|Gets or sets the signature image file name.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top.
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin.
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Opacity|double|Gets or sets the additional opacity for sign image (value from 0.0 (clear) through 1.0 (opaque)). By default the value is 1.0.
|OptionsType|string|The class name of options object, should always contains value "PdfSignImageOptionsData". This property is set automatically when using SDK classes.

## SlidesSignImageOptionsData Object

Provides options to put Image Signature on Slides Documents

```javascript
{
  "left": 10,
  "top": 10,
  "width": 200,
  "height": 100,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "rotationAngle": 90,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "marginMeasureType": "Pixels",
  "opacity": 0.9,
  "signAllPages": false,
  "documentPageNumber": 1,
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
  "optionsType": "SlidesSignImageOptionsData"
}
```

 SlidesSignImageOptionsData Object Fields

|Name|Type|Description
|---|---|---
|ImageGuid|string|Gets or sets the signature image file name.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top.
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin.
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Opacity|double|Gets or sets the signature opacity (value from 0.0 (clear) through 1.0 (opaque)).
|OptionsType|string|The class name of options object, should always contains value "SlidesSignImageOptionsData". This property is set automatically when using SDK classes.

## WordsSignImageOptionsData Object

Provides options to put Image Signature on Words Documents

Example WordsSignImageOptionsData object.

```javascript
{
  "imageGuid": "images\signature_01.jpg",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 100,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "marginMeasureType": "Pixels",
  "opacity": 0.9,
  "signAllPages": false,
  "documentPageNumber": 1,
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
  "optionsType": "WordsSignImageOptionsData"
}
```

 WordsSignImagesOptionsData Object Fields

|Name|Type|Description
|---|---|---
|ImageGuid|string|Gets or sets the signature image file name.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top.
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin.
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Opacity|double|Gets or sets the signature opacity (value from 0.0 (clear) through 1.0 (opaque)).
|OptionsType|string|The class name of options object, should always contains value "WordsSignImageOptionsData". This property is set automatically when using SDK classes.

## CellsSignDigitalOptionsData Object

Provides options to add Digital Signature on Cells Documents

Example CellsSignDigitalOptionsData object.

```javascript
{
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "sheetNumber": 1,
  "rowNumber": 2,
  "columnNumber": 2,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "marginMeasureType": "Pixels",
  "password": "1234567890",
  "certificateGuid": "certificates\SherlockHolmes.pfx",
  "imageGuid": "images\signature_01.jpg",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 100,
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "opacity": 0.9,
  "signAllPages": false,
  "documentPageNumber": 1,
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
  "optionsType": "CellsSignDigitalOptionsData"
}
```

 CellsSignDigitalOptionsData Object Fields

|Name|Type|Description
|---|---|---
|CertificateGuid|string|Gets or sets the digital certificate file GUID.
|Password|string|Gets or sets the password of digital certificate.
|ImageGuid|string|Gets or sets the signature image file name.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SheetNumber|int|Gets or sets worksheet number for signing. DocumentPageNumber parameter contains the same value.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height. (This property is obsolete.)
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|RowNumber|int|Gets or sets the top row number of signature (min value is 0). Top parameter contains the same value.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|ColumnNumber|int|Gets or sets the left column number of signature (min value is 0). Left parameter contains the same value.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top. (This property is obsolete.)
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin. (This property is obsolete.)
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Opacity|double|Gets or sets the additional opacity for sign image (value from 0.0 (clear) through 1.0 (opaque)). By default the value is 1.0.
|OptionsType|string|The class name of options object, should always contains value "CellsSignImageOptionsData". This property is set automatically when using SDK classes

## PdfSignDigitalOptionsData Object

Provides options to put Digital Signature on Pdf Documents

Example PdfSignDigitalOptionsData object.

```javascript
{
  "reason": "reason",
  "contact": "contact",
  "location": "location",
  "visible": true,
  "password": "1234567890",
  "certificateGuid": "certificates\SherlockHolmes.pfx",
  "imageGuid": "images\signature_01.jpg",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 100,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "marginMeasureType": "Pixels",
  "opacity": 0.9,
  "signAllPages": false,
  "documentPageNumber": 1,
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
  "optionsType": "PdfSignDigitalOptionsData"
}
```

 PdfSignDigitalOptionsData Object Fields

|Name|Type|Description
|---|---|---
|CertificateGuid|string|Gets or sets the digital certificate file GUID.
|Password|string|Gets or sets the password of digital certificate.
|ImageGuid|string|Gets or sets the signature image file name.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top.
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin.
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Opacity|double|Gets or sets the additional opacity for sign image (value from 0.0 (clear) through 1.0 (opaque)). By default the value is 1.0.
|Reason|string|Gets or sets the reason of signature.
|Contact|string|Gets or sets the signature contact.
|Location|string|Gets or sets the signature location.
|Visible|bool|Gets or sets the visibility of signature.
|OptionsType|string|The class name of options object, should always contains value "PdfSignDigitalOptionsData". This property is set automatically when using SDK classes

## WordsSignDigitalOptionsData Object

Provides options to put Digital Siganture on Words Documents.

Example WordsSignDigitalOptionsData object.

```javascript
{
  "password": "1234567890",
  "certificateGuid": "certificates\SherlockHolmes.pfx",
  "imageGuid": "images\signature_01.jpg",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 100,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "marginMeasureType": "Pixels",
  "opacity": 0.9,
  "signAllPages": false,
  "documentPageNumber": 1,
  "pagesSetup": {
    "firstPage": true,
    "lastPage": false,
    "oddPages": false,
    "evenPages": false,
    "pageNumbers": [
      1
    ]
  },
  "optionsType": "WordsSignDigitalOptionsData"
}
```

 WordsSignDigitalOptionsData Object Fileds

|Name|Type|Description
|---|---|---
|CertificateGuid|string|Gets or sets the digital certificate file GUID.
|Password|string|Gets or sets the password of digital certificate.
|ImageGuid|string|Gets or sets the signature image file name.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top.
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin.
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Opacity|double|Gets or sets the additional opacity for sign image (value from 0.0 (clear) through 1.0 (opaque)). By default the value is 1.0.
|OptionsType|string|The class name of options object, should always contains value "WordsSignDigitalOptionsData". This property is set automatically when using SDK classes.

## CellsSignBarcodeOptionsData Object

Provides options for Cells Documents to add Barcode Signature.

Example CellsSignBarcodeOptionsData object

```javascript
{
  "sheetNumber": 1,
  "rowNumber": 2,
  "columnNumber": 2,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "marginMeasureType": "Pixels",
  "barcodeTypeName": "Code39Standard",
  "borderVisiblity": true,
  "borderDashStyle": "Dash",
  "borderWeight": 12.0,
  "opacity": 1.0,
  "codeTextAlignment": "None",
  "innerMargins": {
    "all": 2,
    "left": 2,
    "top": 2,
    "right": 2,
    "bottom": 2
  },
  "text": "123456789012",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 100,
  "stretch": "None",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "signAllPages": false,
  "font": {
    "fontFamily": "Times New Roman",
    "fontSize": 14.0,
    "bold": false,
    "italic": false,
    "underline": false
  },
  "foreColor": {
    "Web": "DarkOrange"
  },
  "borderColor": {
    "Web": "DarkOrange"
  },
  "backgroundColor": {
    "Web": "BlueViolet"
  },
  "documentPageNumber": 1,
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
  "optionsType": "CellsSignBarcodeOptionsData"
}
```

 CellsSignBarcodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|Text|string|Text of Signature. Default value is empty.
|BarcodeTypeName|string|Get or set Barcode type. Pick one from supported Barcode Types list.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SheetNumber|int|Gets or sets worksheet number for signing. DocumentPageNumber parameter contains the same value.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height. (This property is obsolete.)
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|RowNumber|int|Gets or sets the top row number of signature (min value is 0).Top parameter contains the same value.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|ColumnNumber|int|Gets or sets the left column number of signature (min value is 0). Left parameter contains the same value.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top. (This property is obsolete.)
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin. (This property is obsolete.)
|BackgroundColor|Color|Gets or sets the background color of signature.
|BorderColor|Color|Gets or sets the border color of signature.
|ForeColor|Color|Gets or sets the fore color of signature.
|Font|SignatureFontData|Gets or sets the font of signature.
|BorderVisiblity|bool|Enables Signature border. Default value is true.
|BorderDashStyle|DashStyleData|Gets or sets the signature border style.
|BorderWeight|int|Specifies Border Width of Signature Area
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Stretch|enum|Specifies stretch mode for Signature. Values are  None, PageWidth, PageHeight, PageArea.
|CodeTextAlignment|enum|Gets or sets the alignment of text in the result Barcode. Default value is None.
|InnerMargins|PaddingData|Gets or sets the space between Barcode elements and result image borders.
|OptionsType|string|The class name of options object, should always contains value "CellsSignBarcodeOptionsData". This property is set automatically when using SDK classes.

## ImagesSignBarcodeOptionsData Object

Provides options for Images Documents to add Barcode Signature.

Example ImagesSignBarcodeOptionsData object.

```javascript
{
  "barcodeTypeName": "Code39Standard",
  "borderVisiblity": true,
  "borderDashStyle": "Dash",
  "borderWeight": 12.0,
  "opacity": 1.0,
  "codeTextAlignment": "None",
  "innerMargins": {
    "all": 2,
    "left": 2,
    "top": 2,
    "right": 2,
    "bottom": 2
  },
  "text": "123456789012",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 100,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "stretch": "None",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "marginMeasureType": "Pixels",
  "signAllPages": false,
  "font": {
    "fontFamily": "Times New Roman",
    "fontSize": 14.0,
    "bold": false,
    "italic": false,
    "underline": false
  },
  "foreColor": {
    "Web": "DarkOrange"
  },
  "borderColor": {
    "Web": "DarkOrange"
  },
  "backgroundColor": {
    "Web": "BlueViolet"
  },
  "documentPageNumber": 1,
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
  "optionsType": "ImagesSignBarcodeOptionsData"
}
```

 ImagesSignBarcodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|Text|string|Text of Signature. Default value is empty.
|BarcodeTypeName|string|Get or set Barcode type. Pick one from supported Barcode Types list.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top.
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin.
|BackgroundColor|Color|Gets or sets the background color of signature.
|BorderColor|Color|Gets or sets the border color of signature.
|ForeColor|Color|Gets or sets the fore color of signature.
|Font|SignatureFontData|Gets or sets the font of signature.
|BorderVisiblity|bool|Enables Signature border. Default value is true.
|BorderDashStyle|DashStyleData|Gets or sets the signature border style.
|BorderWeight|int|Specifies Border Width of Signature Area
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Stretch|enum|Specifies stretch mode for Signature. Values are  None, PageWidth, PageHeight, PageArea.
|Opacity|double|Gets or sets the signature opacity (value from 0.0 (clear) through 1.0 (opaque)).
|CodeTextAlignment|enum|Gets or sets the alignment of text in the result Barcode. Default value is None.
|InnerMargins|PaddingData|Gets or sets the space between Barcode elements and result image borders.
|OptionsType|string|The class name of options object, should always contains value "ImagesSignBarcodeOptionsData". This property is set automatically when using SDK classes.

## PdfSignBarcodeOptionsData object

Provides options for Pdf Documents to add Barcode Signature.

Example PdfSignBarcodeOptionsData object

```javascript
{
  "barcodeTypeName": "Code39Standard",
  "borderVisiblity": true,
  "borderDashStyle": "Dash",
  "borderWeight": 12.0,
  "opacity": 1.0,
  "codeTextAlignment": "None",
  "innerMargins": {
    "all": 2,
    "left": 2,
    "top": 2,
    "right": 2,
    "bottom": 2
  },
  "text": "123456789012",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 100,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "stretch": "None",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "marginMeasureType": "Pixels",
  "signAllPages": false,
  "font": {
    "fontFamily": "Times New Roman",
    "fontSize": 14.0,
    "bold": false,
    "italic": false,
    "underline": false
  },
  "foreColor": {
    "Web": "DarkOrange"
  },
  "borderColor": {
    "Web": "DarkOrange"
  },
  "backgroundColor": {
    "Web": "BlueViolet"
  },
  "documentPageNumber": 1,
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
  "optionsType": "PdfSignBarcodeOptionsData"
}
```

 PdfSignBarcodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|Text|string|Text of Signature. Default value is empty.
|BarcodeTypeName|string|Get or set Barcode type. Pick one from supported Barcode Types list.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top.
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin.
|BackgroundColor|Color|Gets or sets the background color of signature.
|BorderColor|Color|Gets or sets the border color of signature.
|ForeColor|Color|Gets or sets the fore color of signature.
|Font|SignatureFontData|Gets or sets the font of signature.
|BorderVisiblity|bool|Enables Signature border. Default value is true.
|BorderDashStyle|DashStyleData|Gets or sets the signature border style.
|BorderWeight|int|Specifies Border Width of Signature Area
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Stretch|enum|Specifies stretch mode for Signature. Values are  None, PageWidth, PageHeight, PageArea.
|Opacity|double|Gets or sets the signature opacity (value from 0.0 (clear) through 1.0 (opaque)).
|CodeTextAlignment|enum|Gets or sets the alignment of text in the result Barcode. Default value is None.
|InnerMargins|PaddingData|Gets or sets the space between Barcode elements and result image borders.
|OptionsType|string|The class name of options object, should always contains value "PdfSignBarcodeOptionsData". This property is set automatically when using SDK classes.

## SlidesSignBarcodeOptionsData Object

Provides options to put Barcode Signature on Slides Documents.

Example SlidesSignBarcodeOptionsData object

```javascript
{
  "barcodeTypeName": "Code39Standard",
  "borderVisiblity": true,
  "borderDashStyle": "Dash",
  "borderWeight": 12.0,
  "opacity": 1.0,
  "codeTextAlignment": "None",
  "innerMargins": {
    "all": 2,
    "left": 2,
    "top": 2,
    "right": 2,
    "bottom": 2
  },
  "text": "123456789012",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 100,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "stretch": "None",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "marginMeasureType": "Pixels",
  "signAllPages": false,
  "font": {
    "fontFamily": "Times New Roman",
    "fontSize": 14.0,
    "bold": false,
    "italic": false,
    "underline": false
  },
  "foreColor": {
    "Web": "DarkOrange"
  },
  "borderColor": {
    "Web": "DarkOrange"
  },
  "backgroundColor": {
    "Web": "BlueViolet"
  },
  "documentPageNumber": 1,
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
  "optionsType": "SlidesSignBarcodeOptionsData"
}
```

 SlidesSignBarcodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|Text|string|Text of Signature. Default value is empty.
|BarcodeTypeName|string|Get or set Barcode type. Pick one from supported Barcode Types list.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top.
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin.
|BackgroundColor|Color|Gets or sets the background color of signature.
|BorderColor|Color|Gets or sets the border color of signature.
|ForeColor|Color|Gets or sets the fore color of signature.
|Font|SignatureFontData|Gets or sets the font of signature.
|BorderVisiblity|bool|Enables Signature border. Default value is true.
|BorderDashStyle|DashStyleData|Gets or sets the signature border style.
|BorderWeight|int|Specifies Border Width of Signature Area
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Stretch|enum|Specifies stretch mode for Signature. Values are  None, PageWidth, PageHeight, PageArea.
|Opacity|double|Gets or sets the signature opacity (value from 0.0 (clear) through 1.0 (opaque)).
|CodeTextAlignment|enum|Gets or sets the alignment of text in the result Barcode. Default value is None.
|InnerMargins|PaddingData|Gets or sets the space between Barcode elements and result image borders.
|OptionsType|string|The class name of options object, should always contains value "SlidesSignBarcodeOptionsData". This property is set automatically when using SDK classes.

## WordsSignBarcodeOptionsData Object

Provides options for Barcode Signature object for Words Documents.

Example WordsSignBarcodeOptionsData object

```javascript
{
  "barcodeTypeName": "Code39Standard",
  "borderVisiblity": true,
  "borderDashStyle": "Dash",
  "borderWeight": 12.0,
  "opacity": 1.0,
  "codeTextAlignment": "None",
  "innerMargins": {
    "all": 2,
    "left": 2,
    "top": 2,
    "right": 2,
    "bottom": 2
  },
  "text": "123456789012",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 100,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "stretch": "None",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "marginMeasureType": "Pixels",
  "signAllPages": false,
  "font": {
    "fontFamily": "Times New Roman",
    "fontSize": 14.0,
    "bold": false,
    "italic": false,
    "underline": false
  },
  "foreColor": {
    "Web": "DarkOrange"
  },
  "borderColor": {
    "Web": "DarkOrange"
  },
  "backgroundColor": {
    "Web": "BlueViolet"
  },
  "documentPageNumber": 1,
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
  "optionsType": "WordsSignBarcodeOptionsData"
}
```

 WordsSignBarcodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|Text|string|Text of Signature. Default value is empty.
|BarcodeTypeName|string|Get or set Barcode type. Pick one from supported Barcode Types list.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top.
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin.
|BackgroundColor|Color|Gets or sets the background color of signature.
|BorderColor|Color|Gets or sets the border color of signature.
|ForeColor|Color|Gets or sets the fore color of signature.
|Font|SignatureFontData|Gets or sets the font of signature.
|BorderVisiblity|bool|Enables Signature border. Default value is true.
|BorderDashStyle|DashStyleData|Gets or sets the signature border style.
|BorderWeight|int|Specifies Border Width of Signature Area
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Stretch|enum|Specifies stretch mode for Signature. Values are  None, PageWidth, PageHeight, PageArea.
|Opacity|double|Gets or sets the signature opacity (value from 0.0 (clear) through 1.0 (opaque)).
|CodeTextAlignment|enum|Gets or sets the alignment of text in the result Barcode. Default value is None.
|InnerMargins|PaddingData|Gets or sets the space between Barcode elements and result image borders.
|OptionsType|string|The class name of options object, should always contains value "WordsSignBarcodeOptionsData". This property is set automatically when using SDK classes.

## CellsSignQRCodeOptionsData Object

Provides options for Cells Documents to add QR-Code Signature.

Example CellsSignQRCodeOptionsData object

```javascript
{
  "sheetNumber": 1,
  "rowNumber": 2,
  "columnNumber": 2,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "marginMeasureType": "Pixels",
  "qrCodeTypeName": "Aztec",
  "borderVisiblity": true,
  "borderDashStyle": "Dash",
  "borderWeight": 12.0,
  "opacity": 0.8,
  "codeTextAlignment": "None",
  "innerMargins": {
    "all": 2,
    "left": 2,
    "top": 2,
    "right": 2,
    "bottom": 2
  },
  "text": "John Smith",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 100,
  "stretch": "None",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "signAllPages": false,
  "font": {
    "fontFamily": "Times New Roman",
    "fontSize": 14.0,
    "bold": false,
    "italic": false,
    "underline": false
  },
  "foreColor": {
    "Web": "DarkOrange"
  },
  "borderColor": {
    "Web": "DarkOrange"
  },
  "backgroundColor": {
    "Web": "BlueViolet"
  },
  "documentPageNumber": 1,
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
  "optionsType": "CellsSignQRCodeOptionsData"
}
```

 CellsSignQRCodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|Text|string|Text of Signature. Default value is empty.
|QRCodeTypeName|string|Get or set QRCode type. Pick one from supported QRCode Types list.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SheetNumber|int|Gets or sets worksheet number for signing. DocumentPageNumber parameter contains the same value.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height. (This property is obsolete.)
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|RowNumber|int|Gets or sets the top row number of signature (min value is 0).Top parameter contains the same value.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|ColumnNumber|int|Gets or sets the left column number of signature (min value is 0). Left parameter contains the same value.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top. (This property is obsolete.)
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin. (This property is obsolete.)
|BackgroundColor|Color|Gets or sets the background color of signature.
|BorderColor|Color|Gets or sets the border color of signature.
|ForeColor|Color|Gets or sets the fore color of signature.
|Font|SignatureFontData|Gets or sets the font of signature.
|BorderVisiblity|bool|Enables Signature border. Default value is true.
|BorderDashStyle|DashStyleData|Gets or sets the signature border style.
|BorderWeight|int|Specifies Border Width of Signature Area
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Stretch|enum|Specifies stretch mode for Signature. Values are  None, PageWidth, PageHeight, PageArea.
|CodeTextAlignment|enum|Gets or sets the alignment of text in the result QR-code. Default value is None.
|InnerMargins|PaddingData|Gets or sets the space between QR-code elements and result image borders.
|OptionsType|string|The class name of options object, should always contains value "CellsSignQRCodeOptionsData". This property is set automatically when using SDK classes.

## ImagesSignQRCodeOptionsData Object

Provides options for Images Documents to add QRCode Signature.

Example ImagesSignQRCodeOptionsData object.

```javascript
{
  "qrCodeTypeName": "Aztec",
  "borderVisiblity": true,
  "borderDashStyle": "Dash",
  "borderWeight": 12.0,
  "opacity": 0.8,
  "codeTextAlignment": "None",
  "innerMargins": {
    "all": 2,
    "left": 2,
    "top": 2,
    "right": 2,
    "bottom": 2
  },
  "text": "123456789012",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 100,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "stretch": "None",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "marginMeasureType": "Pixels",
  "signAllPages": false,
  "font": {
    "fontFamily": "Times New Roman",
    "fontSize": 14.0,
    "bold": false,
    "italic": false,
    "underline": false
  },
  "foreColor": {
    "Web": "DarkOrange"
  },
  "borderColor": {
    "Web": "DarkOrange"
  },
  "backgroundColor": {
    "Web": "BlueViolet"
  },
  "documentPageNumber": 1,
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
  "optionsType": "ImagesSignQRCodeOptionsData"
}
```

 ImagesSignQRCodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|Text|string|Text of Signature. Default value is empty.
|QRCodeTypeName|string|Get or set QRCode type. Pick one from supported QRCode Types list.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top.
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin.
|BackgroundColor|Color|Gets or sets the background color of signature.
|BorderColor|Color|Gets or sets the border color of signature.
|ForeColor|Color|Gets or sets the fore color of signature.
|Font|SignatureFontData|Gets or sets the font of signature.
|BorderVisiblity|bool|Enables Signature border. Default value is true.
|BorderDashStyle|DashStyleData|Gets or sets the signature border style.
|BorderWeight|int|Specifies Border Width of Signature Area
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Stretch|enum|Specifies stretch mode for Signature. Values are  None, PageWidth, PageHeight, PageArea.
|Opacity|double|Gets or sets the signature opacity (value from 0.0 (clear) through 1.0 (opaque)).
|CodeTextAlignment|enum|Gets or sets the alignment of text in the result QR-code. Default value is None.
|InnerMargins|PaddingData|Gets or sets the space between QR-code elements and result image borders.
|OptionsType|string|The class name of options object, should always contains value "ImagesSignQRCodeOptionsData". This property is set automatically when using SDK classes.

## PdfSignQRCodeOptionsData object

Provides options for Pdf Documents to add QRCode Signature.

Example PdfSignQRCodeOptionsData object

```javascript
{
  "qrCodeTypeName": "Aztec",
  "borderVisiblity": true,
  "borderDashStyle": "Dash",
  "borderWeight": 12.0,
  "opacity": 0.8,
  "codeTextAlignment": "None",
  "innerMargins": {
    "all": 2,
    "left": 2,
    "top": 2,
    "right": 2,
    "bottom": 2
  },
  "text": "123456789012",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 100,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "stretch": "None",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "marginMeasureType": "Pixels",
  "signAllPages": false,
  "font": {
    "fontFamily": "Times New Roman",
    "fontSize": 14.0,
    "bold": false,
    "italic": false,
    "underline": false
  },
  "foreColor": {
    "Web": "DarkOrange"
  },
  "borderColor": {
    "Web": "DarkOrange"
  },
  "backgroundColor": {
    "Web": "BlueViolet"
  },
  "documentPageNumber": 1,
  "pagesSetup": {
    "firstPage": true,
    "lastPage": false,
    "oddPages": false,
    "evenPages": false,
    "pageNumbers": [
      1
    ]
  },
  "optionsType": "PdfSignQRCodeOptionsData"
}
```

 PdfSignQRCodeOptions Object Fields

|Name|Type|Description
|---|---|---
|Text|string|Text of Signature. Default value is empty.
|QRCodeTypeName|string|Get or set QRCode type. Pick one from supported QRCode Types list.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top.
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin.
|BackgroundColor|Color|Gets or sets the background color of signature.
|BorderColor|Color|Gets or sets the border color of signature.
|ForeColor|Color|Gets or sets the fore color of signature.
|Font|SignatureFontData|Gets or sets the font of signature.
|BorderVisiblity|bool|Enables Signature border. Default value is true.
|BorderDashStyle|DashStyleData|Gets or sets the signature border style.
|BorderWeight|int|Specifies Border Width of Signature Area
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Stretch|enum|Specifies stretch mode for Signature. Values are  None, PageWidth, PageHeight, PageArea.
|Opacity|double|Gets or sets the signature opacity (value from 0.0 (clear) through 1.0 (opaque)).
|CodeTextAlignment|enum|Gets or sets the alignment of text in the result QR-code. Default value is None.
|InnerMargins|PaddingData|Gets or sets the space between QR-code elements and result image borders.
|OptionsType|string|The class name of options object, should always contains value "PdfSignQRCodeOptionsData". This property is set automatically when using SDK classes.

## SlidesSignQRCodeOptionsData Object

Provides options to put QR-Code Signature on Slides Documents.

Example SlidesSignQRCodeOptionsData object

```javascript
{
  "qrCodeTypeName": "Aztec",
  "borderVisiblity": true,
  "borderDashStyle": "Dash",
  "borderWeight": 12.0,
  "opacity": 0.8,
  "codeTextAlignment": "None",
  "innerMargins": {
    "all": 2,
    "left": 2,
    "top": 2,
    "right": 2,
    "bottom": 2
  },
  "text": "123456789012",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 100,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "stretch": "None",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "marginMeasureType": "Pixels",
  "signAllPages": false,
  "font": {
    "fontFamily": "Times New Roman",
    "fontSize": 14.0,
    "bold": false,
    "italic": false,
    "underline": false
  },
  "foreColor": {
    "Web": "DarkOrange"
  },
  "borderColor": {
    "Web": "DarkOrange"
  },
  "backgroundColor": {
    "Web": "BlueViolet"
  },
  "documentPageNumber": 1,
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
  "optionsType": "SlidesSignQRCodeOptionsData"
}
```

 SlidesSignQRCodeOptionsData Object Fields

|Name|Type|Description
|---|---|---
|Text|string|Text of Signature. Default value is empty.
|QRCodeTypeName|string|Get or set QRCode type. Pick one from supported QRCode Types list.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top.
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin.
|BackgroundColor|Color|Gets or sets the background color of signature.
|BorderColor|Color|Gets or sets the border color of signature.
|ForeColor|Color|Gets or sets the fore color of signature.
|Font|SignatureFontData|Gets or sets the font of signature.
|BorderVisiblity|bool|Enables Signature border. Default value is true.
|BorderDashStyle|DashStyleData|Gets or sets the signature border style.
|BorderWeight|int|Specifies Border Width of Signature Area
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Stretch|enum|Specifies stretch mode for Signature. Values are  None, PageWidth, PageHeight, PageArea.
|Opacity|double|Gets or sets the signature opacity (value from 0.0 (clear) through 1.0 (opaque)).
|CodeTextAlignment|enum|Gets or sets the alignment of text in the result QR-code. Default value is None.
|InnerMargins|PaddingData|Gets or sets the space between QR-code elements and result image borders.
|OptionsType|string|The class name of options object, should always contains value "SlidesSignQRCodeOptionsData". This property is set automatically when using SDK classes.

## WordsSignQRCodeOptionsData Object

Provides options for QR-Code Signature object for Words Documents.

Example WordsSignQRCodeOptionsData object

```javascript
{
  "qrCodeTypeName": "Aztec",
  "borderVisiblity": true,
  "borderDashStyle": "Dash",
  "borderWeight": 12.0,
  "opacity": 0.8,
  "codeTextAlignment": "None",
  "innerMargins": {
    "all": 2,
    "left": 2,
    "top": 2,
    "right": 2,
    "bottom": 2
  },
  "text": "123456789012",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 100,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "stretch": "None",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "marginMeasureType": "Pixels",
  "signAllPages": false,
  "font": {
    "fontFamily": "Times New Roman",
    "fontSize": 14.0,
    "bold": false,
    "italic": false,
    "underline": false
  },
  "foreColor": {
    "Web": "DarkOrange"
  },
  "borderColor": {
    "Web": "DarkOrange"
  },
  "backgroundColor": {
    "Web": "BlueViolet"
  },
  "documentPageNumber": 1,
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
  "optionsType": "WordsSignQRCodeOptionsData"
}
```

 WordsSignQRCodeOptions Object Fields

|Name|Type|Description
|---|---|---
|Text|string|Text of Signature. Default value is empty.
|QRCodeTypeName|string|Get or set QRCode type. Pick one from supported QRCode Types list.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top.
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin.
|BackgroundColor|Color|Gets or sets the background color of signature.
|BorderColor|Color|Gets or sets the border color of signature.
|ForeColor|Color|Gets or sets the fore color of signature.
|Font|SignatureFontData|Gets or sets the font of signature.
|BorderVisiblity|bool|Enables Signature border. Default value is true.
|BorderDashStyle|DashStyleData|Gets or sets the signature border style.
|BorderWeight|int|Specifies Border Width of Signature Area
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Stretch|enum|Specifies stretch mode for Signature. Values are  None, PageWidth, PageHeight, PageArea.
|Opacity|double|Gets or sets the signature opacity (value from 0.0 (clear) through 1.0 (opaque)).
|CodeTextAlignment|enum|Gets or sets the alignment of text in the result QR-code. Default value is None.
|InnerMargins|PaddingData|Gets or sets the space between QR-code elements and result image borders.
|OptionsType|string|The class name of options object, should always contains value "WordsSignQRCodeOptionsData". This property is set automatically when using SDK classes.

## CellsSignStampOptionsData Object

Provides options to put Stamp Signature on Cells Documents Pages.

Example CellsSignStampOptionsData object

```javascript
{
  "sheetNumber": 1,
  "rowNumber": 2,
  "columnNumber": 2,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "marginMeasureType": "Pixels",
  "outerLines": [
    {
      "height": 20,
      "backgroundColor": {
        "Web": "BlueViolet"
      },
      "text": "John Smith",
      "font": {
        "fontFamily": "Arial",
        "fontSize": 12.0,
        "bold": true,
        "italic": true,
        "underline": true
      },
      "textColor": {
        "Web": "Gold"
      },
      "textBottomIntent": 5,
      "textRepeatType": "FullTextRepeat",
      "outerBorder": {
        "style": "LongDashDot",
        "transparency": 0.7,
        "weight": 1.4,
        "color": {
          "Web": "DarkOrange"
        }
      },
      "innerBorder": {
        "style": "LongDash",
        "transparency": 0.5,
        "weight": 1.2,
        "color": {
          "Web": "DarkOrange"
        }
      },
      "visible": true
    }
  ],
  "innerLines": [
    {
      "height": 30,
      "backgroundColor": {
        "Web": "CornflowerBlue"
      },
      "text": "John Smith",
      "font": {
        "fontFamily": "Times New Roman",
        "fontSize": 20.0,
        "bold": true,
        "italic": true,
        "underline": true
      },
      "textColor": {
        "Web": "Gold"
      },
      "textBottomIntent": 3,
      "textRepeatType": "None",
      "outerBorder": {
        "style": "Dot",
        "transparency": 0.4,
        "weight": 1.4,
        "color": {
          "Web": "GhostWhite"
        }
      },
      "innerBorder": {
        "style": "LongDash",
        "transparency": 0.5,
        "weight": 1.2,
        "color": {
          "Web": "OliveDrab"
        }
      },
      "visible": true
    }
  ],
  "backgroundColor": {
    "Web": "CornflowerBlue"
  },
  "backgroundColorCropType": "InnerArea",
  "backgroundImageCropType": "MiddleArea",
  "imageGuid": "images\signature_01.jpg",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 150,
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "opacity": 0.9,
  "signAllPages": false,
  "documentPageNumber": 1,
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
  "optionsType": "CellsSignStampOptionsData"
}
```

 CellsSignStampOptionsData Object Fields

|Name|Type|Description
|---|---|---
|ImageGuid|string|Gets or sets the signature image file name.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SheetNumber|int|Gets or sets worksheet number for signing. DocumentPageNumber parameter contains the same value.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height. (This property is obsolete.)
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|RowNumber|int|Gets or sets the top row number of signature (min value is 0). Top parameter contains the same value.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|ColumnNumber|int|Gets or sets the left column number of signature (min value is 0). Left parameter contains the same value.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top. (This property is obsolete.)
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin. (This property is obsolete.)
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Opacity|double|Gets or sets the additional opacity for sign image (value from 0.0 (clear) through 1.0 (opaque)). By default the value is 1.0.
|BackgroundColor|Color|Gets or sets the background color of signature.
|BackgroundColorCropType|enum|Gets or sets the background color crop type of signature.
|BackgroundImageCropType|enum|Gets or sets the background image crop type of signature.
|OuterLines|List<StampLineData>|List of Outer Lines rendered as concentric circles.
|InnerLines|List<StampLineData>|List of Inner Lines rendered as set of rectangles.
|OptionsType|string|The class name of options object, should always contains value "CellsSignStampOptionsData". This property is set automatically when using SDK classes.

## ImagesSignStampOptionsData Object

Provides options to put Stamp Signature on Images Documents Pages.

Example ImagesSignStampOptionsData object

```javascript
{
  "outerLines": [
    {
      "height": 20,
      "backgroundColor": {
        "Web": "BlueViolet"
      },
      "text": "John Smith",
      "font": {
        "fontFamily": "Arial",
        "fontSize": 12.0,
        "bold": true,
        "italic": true,
        "underline": true
      },
      "textColor": {
        "Web": "Gold"
      },
      "textBottomIntent": 5,
      "textRepeatType": "FullTextRepeat",
      "outerBorder": {
        "style": "LongDashDot",
        "transparency": 0.7,
        "weight": 1.4,
        "color": {
          "Web": "DarkOrange"
        }
      },
      "innerBorder": {
        "style": "LongDash",
        "transparency": 0.5,
        "weight": 1.2,
        "color": {
          "Web": "DarkOrange"
        }
      },
      "visible": true
    }
  ],
  "innerLines": [
    {
      "height": 30,
      "backgroundColor": {
        "Web": "CornflowerBlue"
      },
      "text": "John Smith",
      "font": {
        "fontFamily": "Times New Roman",
        "fontSize": 20.0,
        "bold": true,
        "italic": true,
        "underline": true
      },
      "textColor": {
        "Web": "Gold"
      },
      "textBottomIntent": 3,
      "textRepeatType": "None",
      "outerBorder": {
        "style": "Dot",
        "transparency": 0.4,
        "weight": 1.4,
        "color": {
          "Web": "GhostWhite"
        }
      },
      "innerBorder": {
        "style": "LongDash",
        "transparency": 0.5,
        "weight": 1.2,
        "color": {
          "Web": "OliveDrab"
        }
      },
      "visible": true
    }
  ],
  "backgroundColor": {
    "Web": "CornflowerBlue"
  },
  "backgroundColorCropType": "InnerArea",
  "backgroundImageCropType": "MiddleArea",
  "imageGuid": "images\signature_01.jpg",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 150,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "marginMeasureType": "Pixels",
  "opacity": 0.9,
  "signAllPages": false,
  "documentPageNumber": 1,
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
  "optionsType": "ImagesSignStampOptionsData"
}
```

 ImagesSignStampOptionsData Object Fields

|Name|Type|Description
|---|---|---
|ImageGuid|string|Gets or sets the signature image file name.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top.
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin.
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Opacity|double|Gets or sets the additional opacity for sign image (value from 0.0 (clear) through 1.0 (opaque)). By default the value is 1.0.
|BackgroundColor|Color|Gets or sets the background color of signature.
|BackgroundColorCropType|enum|Gets or sets the background color crop type of signature.
|BackgroundImageCropType|enum|Gets or sets the background image crop type of signature.
|OuterLines|List<StampLineData>|List of Outer Lines rendered as concentric circles.
|InnerLines|List<StampLineData>|List of Inner Lines rendered as set of rectangles.
|OptionsType|string|The class name of options object, should always contains value "ImagesSignStampOptionsData". This property is set automatically when using SDK classes.

## PdfSignStampOptionsData Object

Provides options to put Stamp Signature on Pdf Documents Pages.

Example PdfSignStampOptionsData object.

```javascript
{
  "outerLines": [
    {
      "height": 20,
      "backgroundColor": {
        "Web": "BlueViolet"
      },
      "text": "John Smith",
      "font": {
        "fontFamily": "Arial",
        "fontSize": 12.0,
        "bold": true,
        "italic": true,
        "underline": true
      },
      "textColor": {
        "Web": "Gold"
      },
      "textBottomIntent": 5,
      "textRepeatType": "FullTextRepeat",
      "outerBorder": {
        "style": "LongDashDot",
        "transparency": 0.7,
        "weight": 1.4,
        "color": {
          "Web": "DarkOrange"
        }
      },
      "innerBorder": {
        "style": "LongDash",
        "transparency": 0.5,
        "weight": 1.2,
        "color": {
          "Web": "DarkOrange"
        }
      },
      "visible": true
    }
  ],
  "innerLines": [
    {
      "height": 30,
      "backgroundColor": {
        "Web": "CornflowerBlue"
      },
      "text": "John Smith",
      "font": {
        "fontFamily": "Times New Roman",
        "fontSize": 20.0,
        "bold": true,
        "italic": true,
        "underline": true
      },
      "textColor": {
        "Web": "Gold"
      },
      "textBottomIntent": 3,
      "textRepeatType": "None",
      "outerBorder": {
        "style": "Dot",
        "transparency": 0.4,
        "weight": 1.4,
        "color": {
          "Web": "GhostWhite"
        }
      },
      "innerBorder": {
        "style": "LongDash",
        "transparency": 0.5,
        "weight": 1.2,
        "color": {
          "Web": "OliveDrab"
        }
      },
      "visible": true
    }
  ],
  "backgroundColor": {
    "Web": "CornflowerBlue"
  },
  "backgroundColorCropType": "InnerArea",
  "backgroundImageCropType": "MiddleArea",
  "imageGuid": "images\signature_01.jpg",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 150,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "marginMeasureType": "Pixels",
  "opacity": 0.9,
  "signAllPages": false,
  "documentPageNumber": 1,
  "pagesSetup": {
    "firstPage": true,
    "lastPage": false,
    "oddPages": false,
    "evenPages": false,
    "pageNumbers": [
      1
    ]
  },
  "optionsType": "PdfSignStampOptionsData"
}
```

 PdfSignStampOptionsData Object Fields

|Name|Type|Description
|---|---|---
|ImageGuid|string|Gets or sets the signature image file name.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top.
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin.
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Opacity|double|Gets or sets the additional opacity for sign image (value from 0.0 (clear) through 1.0 (opaque)). By default the value is 1.0.
|BackgroundColor|Color|Gets or sets the background color of signature.
|BackgroundColorCropType|enum|Gets or sets the background color crop type of signature.
|BackgroundImageCropType|enum|Gets or sets the background image crop type of signature.
|OuterLines|List<StampLineData>|List of Outer Lines rendered as concentric circles.
|InnerLines|List<StampLineData>|List of Inner Lines rendered as set of rectangles.
|OptionsType|string|The class name of options object, should always contains value "PdfSignStampOptionsData". This property is set automatically when using SDK classes.

## SlidesSignStampOptionsData Object

Provides options to put Stamp Signature on Slides Documents Pages.

Example SlidesSignStampOptionsData object

```javascript
{
  "outerLines": [
    {
      "height": 20,
      "backgroundColor": {
        "Web": "BlueViolet"
      },
      "text": "John Smith",
      "font": {
        "fontFamily": "Arial",
        "fontSize": 12.0,
        "bold": true,
        "italic": true,
        "underline": true
      },
      "textColor": {
        "Web": "Gold"
      },
      "textBottomIntent": 5,
      "textRepeatType": "FullTextRepeat",
      "outerBorder": {
        "style": "LongDashDot",
        "transparency": 0.7,
        "weight": 1.4,
        "color": {
          "Web": "DarkOrange"
        }
      },
      "innerBorder": {
        "style": "LongDash",
        "transparency": 0.5,
        "weight": 1.2,
        "color": {
          "Web": "DarkOrange"
        }
      },
      "visible": true
    }
  ],
  "innerLines": [
    {
      "height": 30,
      "backgroundColor": {
        "Web": "CornflowerBlue"
      },
      "text": "John Smith",
      "font": {
        "fontFamily": "Times New Roman",
        "fontSize": 20.0,
        "bold": true,
        "italic": true,
        "underline": true
      },
      "textColor": {
        "Web": "Gold"
      },
      "textBottomIntent": 3,
      "textRepeatType": "None",
      "outerBorder": {
        "style": "Dot",
        "transparency": 0.4,
        "weight": 1.4,
        "color": {
          "Web": "GhostWhite"
        }
      },
      "innerBorder": {
        "style": "LongDash",
        "transparency": 0.5,
        "weight": 1.2,
        "color": {
          "Web": "OliveDrab"
        }
      },
      "visible": true
    }
  ],
  "backgroundColor": {
    "Web": "CornflowerBlue"
  },
  "backgroundColorCropType": "InnerArea",
  "backgroundImageCropType": "MiddleArea",
  "imageGuid": "images\signature_01.jpg",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 150,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "marginMeasureType": "Pixels",
  "opacity": 0.9,
  "signAllPages": false,
  "documentPageNumber": 1,
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
  "optionsType": "SlidesSignStampOptionsData"
}
```

 ImagesSignStampOptionsData Object Fields

|Name|Type|Description
|---|---|---
|ImageGuid|string|Gets or sets the signature image file name.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top.
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin.
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Opacity|double|Gets or sets the additional opacity for sign image (value from 0.0 (clear) through 1.0 (opaque)). By default the value is 1.0.
|BackgroundColor|Color|Gets or sets the background color of signature.
|BackgroundColorCropType|enum|Gets or sets the background color crop type of signature.
|BackgroundImageCropType|enum|Gets or sets the background image crop type of signature.
|OuterLines|List<StampLineData>|List of Outer Lines rendered as concentric circles.
|InnerLines|List<StampLineData>|List of Inner Lines rendered as set of rectangles.
|OptionsType|string|The class name of options object, should always contains value "SlidesSignStampOptionsData". This property is set automatically when using SDK classes.

## WordsSignStampOptionsData Object

Provides options to put Stamp Signature on Words Documents Pages.

Example WordsSignStampOptionsData object

```javascript
{
  "outerLines": [
    {
      "height": 20,
      "backgroundColor": {
        "Web": "BlueViolet"
      },
      "text": "John Smith",
      "font": {
        "fontFamily": "Arial",
        "fontSize": 12.0,
        "bold": true,
        "italic": true,
        "underline": true
      },
      "textColor": {
        "Web": "Gold"
      },
      "textBottomIntent": 5,
      "textRepeatType": "FullTextRepeat",
      "outerBorder": {
        "style": "LongDashDot",
        "transparency": 0.7,
        "weight": 1.4,
        "color": {
          "Web": "DarkOrange"
        }
      },
      "innerBorder": {
        "style": "LongDash",
        "transparency": 0.5,
        "weight": 1.2,
        "color": {
          "Web": "DarkOrange"
        }
      },
      "visible": true
    }
  ],
  "innerLines": [
    {
      "height": 30,
      "backgroundColor": {
        "Web": "CornflowerBlue"
      },
      "text": "John Smith",
      "font": {
        "fontFamily": "Times New Roman",
        "fontSize": 20.0,
        "bold": true,
        "italic": true,
        "underline": true
      },
      "textColor": {
        "Web": "Gold"
      },
      "textBottomIntent": 3,
      "textRepeatType": "None",
      "outerBorder": {
        "style": "Dot",
        "transparency": 0.4,
        "weight": 1.4,
        "color": {
          "Web": "GhostWhite"
        }
      },
      "innerBorder": {
        "style": "LongDash",
        "transparency": 0.5,
        "weight": 1.2,
        "color": {
          "Web": "OliveDrab"
        }
      },
      "visible": true
    }
  ],
  "backgroundColor": {
    "Web": "CornflowerBlue"
  },
  "backgroundColorCropType": "InnerArea",
  "backgroundImageCropType": "MiddleArea",
  "imageGuid": "images\signature_01.jpg",
  "left": 2,
  "top": 2,
  "width": 200,
  "height": 150,
  "locationMeasureType": "Pixels",
  "sizeMeasureType": "Pixels",
  "rotationAngle": 45,
  "horizontalAlignment": "Left",
  "verticalAlignment": "Center",
  "margin": {
    "all": 5,
    "left": 5,
    "top": 5,
    "right": 5,
    "bottom": 5
  },
  "marginMeasureType": "Pixels",
  "opacity": 0.9,
  "signAllPages": false,
  "documentPageNumber": 1,
  "pagesSetup": {
    "firstPage": true,
    "lastPage": false,
    "oddPages": false,
    "evenPages": false,
    "pageNumbers": [
      1
    ]
  },
  "optionsType": "WordsSignStampOptionsData"
}
```

 ImagesSignStampOptionsData Object Fields

|Name|Type|Description
|---|---|---
|ImageGuid|string|Gets or sets the signature image file name.
|DocumentPageNumber|int|Specifies document page number to add Text Signature. Default value is 1.
|SignAllPages|bool|Put signature on all document pages. Default value is false.
|PagesSetup|PagesSetupData|Page options to specify pages to be verified.
|Width|int|The width of Signature Area in measure unit values.
|Height|int|The width of Signature Area in measure unit values.
|SizeMeasureType|enum|Specifies enumeration of Measure Units for Size - Width and Height.
|Top|int|Specifies Y-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|Left|int|Specifies X-coordinate on Document Page of Left-Top corner of Text Signature Area. Default value is 1.
|LocationMeasureType|enum|Specifies enumeration of Measure Units of Location - Left and Top.
|HorizontalAlignment|enum|Setup Horizontal Alignment of Signature Area on Document Page. Possible  values are None, Left, Center, Right.
|VerticalAlignment|enum|Setup Vertical Alignment of Signature Area on Document Page. Possible  values are None, Top, Center, Bottom.
|Margin|PaddingData|Gets or sets the space between Sign and Document edges. Properties are:  All, Left, Top, Right, Bottom.
|MarginMeasureType|enum|Specifies measure type (pixels or percent) for Margin.
|RotationAngle|int|Rotation angle of signature on document page (clockwise).
|Opacity|double|Gets or sets the additional opacity for sign image (value from 0.0 (clear) through 1.0 (opaque)). By default the value is 1.0.
|BackgroundColor|Color|Gets or sets the background color of signature.
|BackgroundColorCropType|enum|Gets or sets the background color crop type of signature.
|BackgroundImageCropType|enum|Gets or sets the background image crop type of signature.
|OuterLines|List<StampLineData>|List of Outer Lines rendered as concentric circles.
|InnerLines|List<StampLineData>|List of Inner Lines rendered as set of rectangles.
|OptionsType|string|The class name of options object, should always contains value "WordsSignStampOptionsData". This property is set automatically when using SDK classes.
