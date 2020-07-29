---
id: "common-structures"
url: "signature/common-structures"
title: "Common structures"
productName: "GroupDocs.Signature Cloud"
weight: 1
description: ""
keywords: ""
---

# Common data structures #

Page contains description for common structures and its properties





## [DocumentType properties]("DocumentTypeObject") ##
|---|---

Specifies enumeration of supported Document Types.

Example **DocumentType** object

```html 
{
	"DocumentType": "Spreadsheet"
}
 ```

 DocumentType Enumeration values (Click here to expand)

|Name|Description
|---|---
|Image|Specifies document images type is used for processing images with formats like .jpg, .png, .tiff and many other
|Pdf|Specifies Pdf document type, type is demanded for processing documents in PDF format
|Presentation|Specifies Presentation document, type is necessary for processing presentations with formats like .ppt, .pptx, .odp and many other
|Spreadsheet|Specifies Spreadsheet document,  type is necessary for processing spreadsheets with formats like .xls, .xlsx, .ods and many other
|WordProcessing|Specifies WordProcessing document, type is used for processing documents with formats like .doc, .docx, .odt and many other







## [SignatureType properties]("SignatureTypeObject") ##
|---|---

Specifies enumeration of supported Signature Types.

Example **SignatureType** object

```html 

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


 

## [PagesSetup properties]("PagesSetupObject") ##
|---|---

Provides options to specify special or ordinary pages for Document processing.

Example **PagesSetup** object

```html 
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

 PagesSetup Object Fields (Click here to expand)

|Name|Type|Description
|---|---|---
|FirstPage|boolean|Specifies if first page of Document should be processed
|LastPage|boolean|Specifies if last page of Document should be processed
|OddPages|boolean|Specifies if odd pages of Document should be processed
|EvenPages|boolean|Specifies if even pages of Document should be processed
|PageNumbers|Array|Specify ordinary pages of Document that should be processed







## [Padding properties]("PaddingObject") ##
|---|---

Provides options to specify special or ordinary pages for Document processing.

Example **Padding** object

```html 
{    
    "All": 5,
    "Left": 5,
    "Top": 5,
    "Right": 5,
    "Bottom": 5
}
 ```

 Padding Object Fields (Click here to expand)

|Name|Type|Description
|---|---|---
|All|int|Gets or sets the padding value for all the edges.
|Left|int|Gets or sets the padding value for the left edge.
|Top|int|Gets or sets the padding value for the top edge.
|Right|int|Gets or sets the padding value for the right edge.
|Bottom|int|Gets or sets the padding value for the bottom edge.







## [SignatureFont Object]("SignatureFontObject") ##
|---|---

Provides properties to specify Font properties for Signature object.

Example SignatureFont object

```html 
{
    "FontFamily": "Times New Roman",
    "FontSize": 14.0,
    "Bold": false,
    "Italic": false,
    "Underline": false
}
 ```

 SignatureFont Object Fields (Click here to expand)

|Name|Type|Description
|---|---|---
|FontFamily|string|Specifies name of Font
|FontSize|int|Sets Font size
|Bold|boolean|Flag is Font is Bold style
|Italic|boolean|Flag is Font is Italic style
|Underline|boolean|Flag is Font is Underline style







## [Color Object]("ColorObject") ##
|---|---

Utility class for Color serialization.

Example Color object

```html 
{
    "Web": "Transparent",
    "Alpha": 0
}
 ```

 Color Object Fields (Click here to expand)

|Name|Type|Description
|---|---|---
|Web|string|HTML string color representation.
|Alpha|int|Alpha component of color structure.







## [MeasureType Object]("MeasureTypeObject") ##
|---|---

Specifies measure units of signature on document page.

Example MeasureType object

```html 
{
	"MeasureType": "Pixels"
}
 ```

 MeasureType Enumeration values (Click here to expand)

|Name|Description
|---|---
|Pixels|Pixels.
|Percent|Percents of page size.
|Millimeters|Millimeters.







## [HorizontalAlignment Object]("HorizontalAlignmentObject") ##
|---|---

Specifies horizontal alignment of element on Document Page.

Example HorizontalAlignment object.

```html 
{
	"HorizontalAlignment": "Left"
}
 ```

 HorizontalAlignment Object Fields (Click here to expand)

|Name|Description
|---|---
|Default|Same as None.
|None|The object is explicitly positioned, usually using its Left property.
|Left|Specifies that the object shall be left aligned to the horizontal alignment base.
|Center|Specifies that the object shall be centered with respect to the horizontal alignment base.
|Right|Specifies that the object shall be right aligned to the horizontal alignment base.







## [VerticalAlignment Object]("VerticalAlignmentObject") ##
|---|---

Specifies vertical alignment of element on Document Page.

Example VerticalAlignment object.

```html 
{
	"VerticalAlignment": "Top"
}
 ```

 VerticalAlignment Object Fields (Click here to expand)

|Name|Description
|---|---
|Default|Same as None.
|None|The object is explicitly positioned, usually using its Top property.
|Top|Specifies that the object shall be at the top of the vertical alignment base.
|Center|Specifies that the object shall be centered with respect to the vertical alignment base.
|Bottom|Specifies that the object shall be at the bottom of the vertical alignment base.







## [TextHorizontalAlignment Object]("TextHorizontalAlignmentDataObject") ##
|---|---

Specifies text horizontal alignment inside a Signature.

Example TextHorizontalAlignment object.

```html 
{
	 "TextHorizontalAlignment": "Left"
}
 ```

 TextHorizontalAlignment Object Fields (Click here to expand)

|Name|Description
|---|---
|Left|Specifies that the text is left aligned to the horizontal alignment base.
|Center|Specifies that the text is centered to the horizontal alignment base.
|Right|Specifies that the text is right aligned to the horizontal alignment base.







## [TextVerticalAlignment Object]("TextVerticalAlignmentDataObject") ##
|---|---

Specifies text vertical alignment inside a Signature.

Example TextVerticalAlignment object.

```html 
{
	"TextVerticalAlignment": "Top"
}
 ```

 TextVerticalAlignment Object Fields (Click here to expand)

|Name|Description
|---|---
|Top|Specifies that the text is top aligned to the vertical alignment base.
|Center|Specifies that the text is centered to the vertical alignment base.
|Bottom|Specifies that the text is bottom aligned to the vertical alignment base.







## [StretchMode Object]("StretchModeDataObject") ##
|---|---

Specifies measure units of signature on document page.

Example StretchMode object.

```html 
{
	"Stretch": "PageHeight"
}
 ```

 StretchMode Object Fields (Click here to expand)

|Name|Description
|---|---
|Default|Default value. No stretch mode will be applied.
|PageWidth|Stretch Signature area along page Width. Margin property will be used to apply required offset values.
|PageHeight|Stretch Signature area along page Height. Margin property will be used to apply required offset values.
|PageArea|Stretch Signature area along page Height and Width. Margin property will be used to apply required offset values.







## [TextSignatureImplementation Object]("TextSignatureImplementationObject") ##
|---|---

Specifies type of implementation for cells Text Signature.

Example CellsTextSignatureImplementation object.

```html 
{
	"SignatureImplementation": "TextAsImage"
}
 ```

 CellsTextSignatureImplementation Object Fields (Click here to expand)

|Name|Description
|---|---
|TextStamp|Text Signature as Label object on Cells sheet.
|TextAsImage|Text Signature as Image object on Cells sheet.






\\

## [DashStyle Object]("DashStyleObject") ##
|---|---

Represents style of dash drawing lines on documents.

Example DashStyle object.

```html 
{
	"BorderDashStyle": "Solid"
}
 ```

 DashStyleData Object Fields (Click here to expand)

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







## [ExtendedDashStyle Object]("ExtendedDashStyleObject") ##
|---|---

Represents style of dash drawing lines on documents.

Example ExtendedDashStyle object.

```html 
{
	"BorderDashStyle": "Solid"
}
 ```

 ExtendedDashStyle Object Fields (Click here to expand)

|Name|Description
|---|---
|Default|Represent a default solid line.
|Solid|Represent a solid line.
|ShortDash|Represent a short dash line.
|ShortDot|Represent a short dot line.
|ShortDashDot|Represent a short dash-dot line.
|ShortDashDotDot|Represent a short dash-dot-dot line.
|Dot|Represent a square dot style.
|Dash|Represent a dash line style.
|LongDash|Represent a long dash style.
|DashDot|Dash short dash.
|LongDashDot|Long dash short dash.
|LongDashDotDot|Long dash short dash short dash.







## [StampBackgroundCropType Object]("StampBackgroundCropTypeObject") ##
|---|---

Specifies crop type of background layer on Stamp elements.

Example StampBackgroundCropType object.

```html 
{
	"BackgroundColorCropType": "InnerArea"
}
 ```

 StampBackgroundCropType Object Fields (Click here to expand)

|Name|Description
|---|---
|None|No crop - all Signature area rectangle will be filled with background.
|OuterArea|Crop background by external outer line.
|MiddleArea|Crop background between external and inner lines.
|InnerArea|Crop background by internal line.







## [StampTextRepeatType Object]("StampTextRepeatTypeObject") ##
|---|---

Specifies type of text repeat for stamp lines.

Example StampTextRepeatType object.

```html 
{
	"TextRepeatType": "FullTextRepeat"
}
 ```

 StampTextRepeatType Object Fields (Click here to expand)

|Name|Description
|---|---
|None|No repeat.
|FullTextRepeat|Text will be repeated to fit full length without truncation.
|RepeatWithTruncation|Text will be repeated to fit full length with word truncation at the end.







## [BorderLine Object]("BorderLineObject") ##
|---|---

Utility class for BorderLine serialization.

Example BorderLine object

```html 
       {
        "style": "LongDash",
        "transparency": 0.5,
        "weight": 1.2,
        "color": {
          "Web": "DarkOrange"
        }
 ```

 BorderLine Object Fields (Click here to expand)

|Name|Type|Description
|---|---|---
|Style|enum|Gets or sets the signature border style.
|Transparency|double|Gets or sets the signature border transparency (value from 0.0 (opaque) through 1.0 (clear)).
|Weight|double|Gets or sets the weight of the signature border.
|Color|Color|Gets or sets the border color of signature.







## [StampLine Object]("StampLineObject") ##
|---|---

Utility class for StampLine serialization.

Example StampLine object

```html 
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

 StampLine Object Fields (Click here to expand)

|Name|Type|Description
|---|---|---
|Height|int|Gets or sets the line height on Stamp.
|BackgroundColor|Color|Gets or sets the background color of signature.
|Text|String|Gets or sets the text of stamp line.
|Font|SignatureFont|Get or set Font of Stamp Line text.
|TextColor|Color|Gets or sets the text color of signature.
|TextBottomIntent|int|Gets or sets the bottom intent of text.
|TextRepeatType|StampTextRepeatType|Gets or sets text repeat type.
|OuterBorder|BorderLine|Setup Outer Border. **.**
|InnerBorder|BorderLine|Setup Inner Border. **.**
|Visible|bool|Get and set visibility of Stamp Line.







## [DigitalSignatureType Object]("DigitalSignatureTypeObject") ##
|---|---

Digital Signature Type define the method to sign.

Example DigitalSignatureType object

```html 
{
  "SignatureType": "CryptoApi"
}
 ```

 DigitalSignatureTypeData Object Fields (Click here to expand)

|Name|Description
|---|---
|Unknown|Indicates an error, unknown digital signature type.
|CryptoApi|The Crypto API signature method used in Microsoft Word 97-2003 .DOC binary documents.
|XmlDsig|The XmlDsig signature method used in OOXML and OpenDocument documents.







## [TextMatchType Object]("TextMatchTypeObject") ##
|---|---

Represents style of dash drawing lines on documents.

Example TextMatchType object

```html 
{
  "MatchType": "Contains"
}
 ```

 TextMatchType Object Fields (Click here to expand)

|Name|Description
|---|---
|Exact|Text is fully match.
|StartsWith|Text starts with value.
|EndsWith|Text ends with value.
|Contains|Text contains the value.







## [CodeTextAlignment Object]("CodeTextAlignmentObject") ##
|---|---

Alignment of code text for Bar-codes and QR-codes.

Example CodeTextAlignment object

```html 
{
  "CodeTextAlignment": "Above"
}
 ```

 CodeTextAlignment Object Fields (Click here to expand)

|Name|Description
|---|---
|None|Text is not visible.
|Above|Text is above the code.
|Below|Text is below the code.
|Right|Text is on the right of the code.







## [Brush Object]("BrushObject") ##
|---|---

Base class for setting signature background brush. There are four subclasses for describing various brushes:**[LinearGradientBrush,]("LinearGradientBrushObject")** **[RadialGradientBrush,]("RadialGradientBrushObject")** **[SolidBrush,]("SolidBrushObject")** **[TextureBrush.]("TextureBrushObject")**
|---|---|---|---|---|---|---|---

## [LinearGradientBrush Object]("LinearGradientBrushObject") ##
|---|---

Example LinearGradientBrush object:

```html 
{
	"startColor": {"web": "CornflowerBlue"}, 
	"endColor": {"web": "DarkBlue"}, 
	"angle": 0.0, 
	"brushType": "LinearGradientBrush"
}
 ```

 LinearGradientBrush Object Fields (Click here to expand)

|Name|Type|Description
|---|---|---
|StartColor|Color|Gets or sets start gradient color.
|EndColor|Color|Gets or sets finish gradient color.
|Angle|float|Gets or sets gradient angle.







## [RadialGradientBrush Object]("RadialGradientBrushObject") ##
|---|---

Example RadialGradientBrush object:

```html 
{
	"innerColor": {"web": "CornflowerBlue"}, 
	"outerColor": {"web": "DarkBlue"}, 
	"brushType": "RadialGradientBrush"
}
 ```

 RadialGradientBrush Object Fields (Click here to expand)

|Name|Type|Description
|---|---|---
|InnerColor|Color|Gets or sets inner gradient color.
|OuterColor|Color|Gets or sets outer gradient color.







## [SolidBrush Object]("SolidBrushObject") ##
|---|---

Example SolidBrush object:

```html 
{
	"color": {"web": "DarkBlue"}, 
	"brushType": "SolidBrush"
}
 ```

 SolidBrush Object Fields (Click here to expand)

|Name|Type|Description
|---|---|---
|Color|Color|Gets or sets color of solid brush.







## [TextureBrush Object]("TextureBrushObject") ##
|---|---

Example TextureBrush object:

```html 
{
	"imageGuid": "images\signature_01.jpg", 
	"brushType": "TextureBrush"
}
 ```

 TextureBrush Object Fields (Click here to expand)

|Name|Type|Description
|---|---|---
|ImageGuid|string|Gets or sets the texture image file Guid.





