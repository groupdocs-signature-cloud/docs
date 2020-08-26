---
id: "common-structures"
url: "signature/common-structures"
title: "Common structures"
productName: "GroupDocs.Signature Cloud"
weight: 1
description: ""
keywords: ""
---

Page contains description for common structures and its properties

## SignatureType properties

Specifies enumeration of supported Signature Types.

Example **SignatureType** object

```javascript
{
 "SignatureType": "Text"
}
```

|Name|Description
|---|---
|Text|Specifies Text signature type
|Image|Specifies Image signature type
|Digital|Specifies Digital signature type
|Barcode|Specifies Barcode signature type
|QRCode|Specifies QRCode signature type
|Stamp|Specifies Stamp signature type

## PagesSetup properties

Provides options to specify special or ordinary pages for Document processing.

Example **PagesSetup** object

```javascript
{
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
  }
}

```

PagesSetup Object Fields

|Name|Type|Description
|---|---|---
|FirstPage|boolean|Specifies if first page of Document should be processed
|LastPage|boolean|Specifies if last page of Document should be processed
|OddPages|boolean|Specifies if odd pages of Document should be processed
|EvenPages|boolean|Specifies if even pages of Document should be processed
|PageNumbers|Array|Specify ordinary pages of Document that should be processed

## Padding properties

Provides options to specify special or ordinary pages for Document processing.

Example of **Padding** object

```javascript
{
    "All": 5,
    "Left": 5,
    "Top": 5,
    "Right": 5,
    "Bottom": 5
}
```

 Padding Object Fields

|Name|Type|Description
|---|---|---
|All|int|Gets or sets the padding value for all the edges.
|Left|int|Gets or sets the padding value for the left edge.
|Top|int|Gets or sets the padding value for the top edge.
|Right|int|Gets or sets the padding value for the right edge.
|Bottom|int|Gets or sets the padding value for the bottom edge.

## SignatureFont Object

Provides properties to specify Font properties for Signature object.

Example SignatureFont object

```javascript
{
    "FontFamily": "Times New Roman",
    "FontSize": 14.0,
    "Bold": false,
    "Italic": false,
    "Underline": false
}

```

SignatureFont Object Fields

|Name|Type|Description
|---|---|---
|FontFamily|string|Specifies name of Font
|FontSize|int|Sets Font size
|Bold|boolean|Flag is Font is Bold style
|Italic|boolean|Flag is Font is Italic style
|Underline|boolean|Flag is Font is Underline style

## Color Object

Utility class for Color serialization.

Example Color object

```javascript
{
    "Web": "Transparent",
    "Alpha": 0
}

```

Color Object Fields

|Name|Type|Description
|---|---|---
|Web|string|HTML string color representation.
|Alpha|int|Alpha component of color structure.

## MeasureType Object

Specifies measure units of signature on document page.

Example MeasureType object

```javascript
{
 "MeasureType": "Pixels"
}

```

MeasureType Enumeration values

|Name|Description
|---|---
|Pixels|Pixels.
|Percent|Percents of page size.
|Millimeters|Millimeters.

## HorizontalAlignment Object

Specifies horizontal alignment of element on Document Page.

Example HorizontalAlignment object.

```javascript
{
 "HorizontalAlignment": "Left"
}

```

HorizontalAlignment Object Fields

|Name|Description
|---|---
|Default|Same as None.
|None|The object is explicitly positioned, usually using its Left property.
|Left|Specifies that the object shall be left aligned to the horizontal alignment base.
|Center|Specifies that the object shall be centered with respect to the horizontal alignment base.
|Right|Specifies that the object shall be right aligned to the horizontal alignment base.

## VerticalAlignment Object

Specifies vertical alignment of element on Document Page.

Example VerticalAlignment object.

```javascript
{
 "VerticalAlignment": "Top"
}

```

VerticalAlignment Object Fields

|Name|Description
|---|---
|Default|Same as None.
|None|The object is explicitly positioned, usually using its Top property.
|Top|Specifies that the object shall be at the top of the vertical alignment base.
|Center|Specifies that the object shall be centered with respect to the vertical alignment base.
|Bottom|Specifies that the object shall be at the bottom of the vertical alignment base.

## TextHorizontalAlignment Object

Specifies text horizontal alignment inside a Signature.

Example TextHorizontalAlignment object.

```javascript
{
  "TextHorizontalAlignment": "Left"
}

```

TextHorizontalAlignment Object Fields

|Name|Description
|---|---
|Left|Specifies that the text is left aligned to the horizontal alignment base.
|Center|Specifies that the text is centered to the horizontal alignment base.
|Right|Specifies that the text is right aligned to the horizontal alignment base.

## TextVerticalAlignment Object

Specifies text vertical alignment inside a Signature.

Example TextVerticalAlignment object.

```javascript
{
 "TextVerticalAlignment": "Top"
}

```

TextVerticalAlignment Object Fields

|Name|Description
|---|---
|Top|Specifies that the text is top aligned to the vertical alignment base.
|Center|Specifies that the text is centered to the vertical alignment base.
|Bottom|Specifies that the text is bottom aligned to the vertical alignment base.

## StretchMode Object

Specifies measure units of signature on document page.

Example StretchMode object.

```javascript
{
 "Stretch": "PageHeight"
}

```

StretchMode Object Fields

|Name|Description
|---|---
|Default|Default value. No stretch mode will be applied.
|PageWidth|Stretch Signature area along page Width. Margin property will be used to apply required offset values.
|PageHeight|Stretch Signature area along page Height. Margin property will be used to apply required offset values.
|PageArea|Stretch Signature area along page Height and Width. Margin property will be used to apply required offset values.

## TextSignatureImplementation Object

Specifies type of implementation for cells Text Signature.

Example CellsTextSignatureImplementation object.

```javascript
{
 "SignatureImplementation": "TextAsImage"
}

```

CellsTextSignatureImplementation Object Fields

|Name|Description
|---|---
|TextStamp|Text Signature as Label object on Cells sheet.
|TextAsImage|Text Signature as Image object on Cells sheet.

## DashStyle Object

Represents style of dash drawing lines on documents.

Example DashStyle object.

```javascript
{
 "BorderDashStyle": "Solid"
}

```

DashStyleData Object Fields

|Name|Description
|---|---
|Dash|Represent a dash line.
|DashDot|Represents a dash-dot line.
|DashDotDot|Represents a dash-dot-dot line.
|DashLongDash|Represents a long dash-short dash line.
|DashLongDashDot|Represents a long dash-short dash-dot line.
|RoundDot|Represents a round-dot line.
|Solid|Represent a solid line.
|SquareDot|Represents a square-dot line.

## StampBackgroundCropType Object

Specifies crop type of background layer on Stamp elements.

Example StampBackgroundCropType object.

```javascript
{
 "BackgroundColorCropType": "InnerArea"
}

```

StampBackgroundCropType Object Fields

|Name|Description
|---|---
|None|No crop - all Signature area rectangle will be filled with background.
|OuterArea|Crop background by external outer line.
|MiddleArea|Crop background between external and inner lines.
|InnerArea|Crop background by internal line.

## StampTextRepeatType Object

Specifies type of text repeat for stamp lines.

Example StampTextRepeatType object.

```javascript
{
 "TextRepeatType": "FullTextRepeat"
}

```

StampTextRepeatType Object Fields

|Name|Description
|---|---
|None|No repeat.
|FullTextRepeat|Text will be repeated to fit full length without truncation.
|RepeatWithTruncation|Text will be repeated to fit full length with word truncation at the end.

## BorderLine Object

Utility class for BorderLine serialization.

Example BorderLine object

```javascript
{
"style": "LongDash",
"transparency": 0.5,
"weight": 1.2,
"color": {
  "Web": "DarkOrange"
}

```

BorderLine Object Fields

|Name|Type|Description
|---|---|---
|Style|enum|Gets or sets the signature border style.
|Transparency|double|Gets or sets the signature border transparency (value from 0.0 (opaque) through 1.0 (clear)).
|Weight|double|Gets or sets the weight of the signature border.
|Color|Color|Gets or sets the border color of signature.

## StampLine Object

Utility class for StampLine serialization.

Example StampLine object

```javascript
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

```

StampLine Object Fields

|Name|Type|Description
|---|---|---
|Height|int|Gets or sets the line height on Stamp.
|BackgroundColor|Color|Gets or sets the background color of signature.
|Text|String|Gets or sets the text of stamp line.
|Font|SignatureFont|Get or set Font of Stamp Line text.
|TextColor|Color|Gets or sets the text color of signature.
|TextBottomIntent|int|Gets or sets the bottom intent of text.
|TextRepeatType|StampTextRepeatType|Gets or sets text repeat type.
|OuterBorder|BorderLine|Setup Outer Border.
|InnerBorder|BorderLine|Setup Inner Border.
|Visible|bool|Get and set visibility of Stamp Line.

## DigitalSignatureType Object

Digital Signature Type define the method to sign.

Example DigitalSignatureType object

```javascript
{
  "SignatureType": "CryptoApi"
}

```

DigitalSignatureTypeData Object Fields

|Name|Description
|---|---
|Unknown|Indicates an error, unknown digital signature type.
|CryptoApi|The Crypto API signature method used in Microsoft Word 97-2003 .DOC binary documents.
|XmlDsig|The XmlDsig signature method used in OOXML and OpenDocument documents.

## TextMatchType Object

Represents style of dash drawing lines on documents.

Example TextMatchType object

```javascript
{
  "MatchType": "Contains"
}

```

TextMatchType Object Fields

|Name|Description
|---|---
|Exact|Text is fully match.
|StartsWith|Text starts with value.
|EndsWith|Text ends with value.
|Contains|Text contains the value.

## CodeTextAlignment Object

Alignment of code text for Bar-codes and QR-codes.

Example CodeTextAlignment object

```javascript
{
  "CodeTextAlignment": "Above"
}

```

CodeTextAlignment Object Fields

|Name|Description
|---|---
|None|Text is not visible.
|Above|Text is above the code.
|Below|Text is below the code.
|Right|Text is on the right of the code.

## Brush Object

Base class for setting signature background brush. There are four subclasses for describing various brushes:**LinearGradientBrush**, **RadialGradientBrush**, **SolidBrush**, **TextureBrush**

## LinearGradientBrush Object

Example LinearGradientBrush object:

```javascript
{
 "startColor": {"web": "CornflowerBlue"},
 "endColor": {"web": "DarkBlue"},
 "angle": 0.0,
 "brushType": "LinearGradientBrush"
}

```

LinearGradientBrush Object Fields

|Name|Type|Description
|---|---|---
|StartColor|Color|Gets or sets start gradient color.
|EndColor|Color|Gets or sets finish gradient color.
|Angle|float|Gets or sets gradient angle.

## RadialGradientBrush Object

Example RadialGradientBrush object:

```javascript
{
 "innerColor": {"web": "CornflowerBlue"},
 "outerColor": {"web": "DarkBlue"},
 "brushType": "RadialGradientBrush"
}

```

RadialGradientBrush Object Fields

|Name|Type|Description
|---|---|---
|InnerColor|Color|Gets or sets inner gradient color.
|OuterColor|Color|Gets or sets outer gradient color.

## SolidBrush Object

Example SolidBrush object:

```javascript
{
 "color": {"web": "DarkBlue"},
 "brushType": "SolidBrush"
}

```

SolidBrush Object Fields

|Name|Type|Description
|---|---|---
|Color|Color|Gets or sets color of solid brush.

## TextureBrush Object

Example TextureBrush object:

```javascript
{
 "imageGuid": "images\signature_01.jpg",
 "brushType": "TextureBrush"
}

```

TextureBrush Object Fields

|Name|Type|Description
|---|---|---
|ImageGuid|string|Gets or sets the texture image file Guid.
