---
id: "sign-document-with-multiple-signature"
url: "signature/sign-document-with-multiple-signature"
title: "Sign document with multiple signature"
productName: "GroupDocs.Signature Cloud"
description: ""
keywords: ""
---

# Introduction #

GroupDocs.Signature Cloud allows to sign document with several signatures simultaneously and even apply signatures of different types to the same document.

API Usage

There are steps that usage of GroupDocs.Signature Cloud consists of:

1. Upload input document into cloud storage and other files, like digital certificate or image stamp
1. Sign document
1. Download output document

For storage operations, like uploading or downloading documents, please refer to the corresponding articles of this manual.

[Swagger UI](https://apireference.groupdocs.cloud/signature/) lets you call this REST API directly from the browser.

## cURL REST Example ##

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}} {{< tab tabNum="1" >}}

```javascript

// First get JSON Web Token
// Please get your Client Id and Client Secret from https://dashboard.groupdocs.cloud/applications. Kindly place Client Id in "client_id" and Client Secret in "client_secret" argument.
curl -v "https://api.groupdocs.cloud/connect/token" \
-X POST \
-d "grant_type#client_credentials&client_id#xxxx&client_secret#xxxx" \
-H "Content-Type: application/x-www-form-urlencoded" \
-H "Accept: application/json"

// cURL example to get document information
curl -v "https://api.groupdocs.cloud/v2.0/signature/create" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>"
-d "{
  'FileInfo': {
    'FilePath': 'one-page.docx'
  },
  'Options': [
    {
      'AllPages': true,
      'SignatureType': 'QRCode',
      'QRCodeType': 'Aztec',
      'Text': '123456789012',
      'Left': 100,
      'Top': 100,
      'Width': 100,
      'Height': 100
    },
    {
      'AllPages': true,
      'SignatureType': 'Text',
      'Text': 'GroupDocs.Signature Cloud',
      'Left': 100,
      'Top': 300,
      'Width': 500,
      'Height': 100,
      'Font': {
          'FontFamily': 'Arial',
          'FontSize': 14,
          'Bold': true
       },
      'ForeColor': { 'Web': 'BlueViolet' }
    }
  ],
  'SaveOptions': {
    'OutputFilePath': 'signedText_one-page.docx'
  }
}"

```

{{< /tab >}} {{< tab tabNum="2" >}}

```javascript

{
  "fileInfo": {
    "filePath": "signedText_one-page.docx",
    "storageName": null,
    "versionId": null,
    "password": null
  },
  "size": 1355095,
  "downloadUrl": "https://api-qa.groupdocs.cloud/v2.0/signature/storage/file/signedText_one-page.docx",
  "succeeded": [
    {
      "qrCodeType": "Aztec",
      "text": "123456789012",
      "format": "Portable Network Graphic",
      "signatureType": "QRCode",
      "pageNumber": 1,
      "signatureId": "3518f886-669b-4cb2-b8c8-5678e47b2731",
      "isSignature": true,
      "createdOn": "2020-07-22T06:41:56.2312011+00:00",
      "modifiedOn": "2020-07-22T06:41:56.2312011+00:00",
      "top": 100,
      "left": 100,
      "width": 100,
      "height": 100
    },
    {
      "text": "GroupDocs.Signature Cloud",
      "signatureImplementation": "Native",
      "signatureType": "Text",
      "pageNumber": 1,
      "signatureId": "2128a0be-cf85-4562-8450-a63ff083dac3",
      "isSignature": true,
      "createdOn": "2020-07-22T06:41:54.6495517+00:00",
      "modifiedOn": "2020-07-22T06:41:54.6495517+00:00",
      "top": 300,
      "left": 100,
      "width": 500,
      "height": 100
    }
  ],
  "failed": []
}

{{< /tab >}} {{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### SDK Examples ###

{{< tabs tabTotal="6" tabID="10" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Python" tabName6="Ruby" >}} {{< tab tabNum="1" >}}

```csharp

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-dotnet-samples
string MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
string MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

var configuration = new Configuration(MyClientId, MyClientSecret);
var apiInstance = new SignApi(configuration);

// Barcode sign options.
var barcodeOptions = new SignBarcodeOptions
{
    SignatureType = SignatureTypeEnum.Barcode,
    Text = "123456789012",
    BarcodeType = "Code128",
    CodeTextAlignment = SignBarcodeOptions.CodeTextAlignmentEnum.None,
    Left = 100,
    Top = 100,
    Width = 300,
    Height = 100,
    LocationMeasureType = SignTextOptions.LocationMeasureTypeEnum.Pixels,
    SizeMeasureType = SignTextOptions.SizeMeasureTypeEnum.Pixels,
    Stretch = SignTextOptions.StretchEnum.None,
    RotationAngle = 0,
    HorizontalAlignment = SignTextOptions.HorizontalAlignmentEnum.None,
    VerticalAlignment = SignTextOptions.VerticalAlignmentEnum.None,
    Margin = new Padding {All = 5},
    MarginMeasureType = SignTextOptions.MarginMeasureTypeEnum.Pixels,
    ForeColor = new Color {Web = "BlueViolet"},
    Border = new BorderLine
    {
        Color = new Color {Web = "DarkOrange"},
        Visible = true,
        Style = BorderLine.StyleEnum.Dash,
        Weight = 12
    },
    BackgroundColor = new Color {Web = "DarkOrange"},
    InnerMargins = new Padding {All = 2},
    AllPages = false,
    Page = 1,
    PagesSetup = new PagesSetup
    {
        EvenPages = false,
        FirstPage = true,
        LastPage = false,
        OddPages = false,
        PageNumbers = new List<int?> {1}
    }
};
// Stamp Sign options.
var stampOptions = new SignStampOptions
{
    SignatureType = SignatureTypeEnum.Stamp,
    ImageFilePath = "signature.jpg",
    Left = 100,
    Top = 100,
    Width = 300,
    Height = 200,
    LocationMeasureType = SignImageOptions.LocationMeasureTypeEnum.Pixels,
    SizeMeasureType = SignImageOptions.SizeMeasureTypeEnum.Pixels,
    RotationAngle = 0,
    HorizontalAlignment = SignImageOptions.HorizontalAlignmentEnum.None,
    VerticalAlignment = SignImageOptions.VerticalAlignmentEnum.None,
    Margin = new Padding {All = 5},
    MarginMeasureType = SignImageOptions.MarginMeasureTypeEnum.Pixels,
    BackgroundColor = new Color {Web = "CornflowerBlue"},
    BackgroundColorCropType = SignStampOptions.BackgroundColorCropTypeEnum.InnerArea,
    BackgroundImageCropType = SignStampOptions.BackgroundImageCropTypeEnum.MiddleArea,
    OuterLines #
        new List<StampLine>
        {
            new StampLine
            {
                Text = "GroupDocs Cloud",
                Font #
                    new SignatureFont
                    {
                        FontFamily = "Arial",
                        FontSize = 12,
                        Bold = true,
                        Italic = true,
                        Underline = true
                    },
                TextBottomIntent = 5,
                TextColor = new Color {Web = "Gold"},
                TextRepeatType = StampLine.TextRepeatTypeEnum.FullTextRepeat,
                BackgroundColor = new Color {Web = "BlueViolet"},
                Height = 20,
                InnerBorder #
                    new BorderLine
                    {
                        Color = new Color {Web = "DarkOrange"},
                        Style = BorderLine.StyleEnum.LongDash,
                        Transparency = 0.5,
                        Weight = 1.2
                    },
                OuterBorder = new BorderLine
                {
                    Color = new Color {Web = "DarkOrange"},
                    Style = BorderLine.StyleEnum.LongDashDot,
                    Transparency = 0.7,
                    Weight = 1.4
                },
                Visible = true
            }
        },
    InnerLines = new List<StampLine>
    {
        new StampLine
        {
            Text = "GroupDocs.Signature Cloud",
            Font #
                new SignatureFont
                {
                    FontFamily = "Times New Roman",
                    FontSize = 20,
                    Bold = true,
                    Italic = true,
                    Underline = true
                },
            TextBottomIntent = 3,
            TextColor = new Color {Web = "Gold"},
            TextRepeatType = StampLine.TextRepeatTypeEnum.None,
            BackgroundColor = new Color {Web = "CornflowerBlue"},
            Height = 30,
            InnerBorder #
                new BorderLine
                {
                    Color = new Color {Web = "OliveDrab"},
                    Style = BorderLine.StyleEnum.LongDash,
                    Transparency = 0.5,
                    Weight = 1.2
                },
            OuterBorder = new BorderLine
            {
                Color = new Color {Web = "GhostWhite"},
                Style = BorderLine.StyleEnum.Dot,
                Transparency = 0.4,
                Weight = 1.4
            },
            Visible = true
        }
    },
    AllPages = false,
    Page = 1,
    PagesSetup = new PagesSetup
    {
        EvenPages = false,
        FirstPage = true,
        LastPage = false,
        OddPages = false,
        PageNumbers = new List<int?> {1}
    }
};
// Sign settings.
var signSettings = new SignSettings
{
    FileInfo = new FileInfo
    {
        FilePath = "one-page.docx"
    },
    SaveOptions = new SaveOptions { OutputFilePath = "signedCollection_one-page.docx", SaveFormat = "docx" },
    Options = new List<SignOptions> { barcodeOptions, stampOptions }
};
// Create request.
var request = new CreateSignaturesRequest(signSettings);
// Call api method with request.
var response = apiInstance.CreateSignatures(request);

```

{{< /tab >}} {{< tab tabNum="2" >}}

```java

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-java-samples
String MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
String MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

Configuration configuration = new Configuration(MyClientId, MyClientSecret);
SignApi apiInstance = new SignApi(configuration);

FileInfo fileInfo = new FileInfo();
fileInfo.setFilePath("Signaturedocs\\one-page.docx");
fileInfo.setPassword(null);
fileInfo.setVersionId(null);
fileInfo.setStorageName(Constants.MYStorage);

InfoSettings infoSettings = new InfoSettings();
infoSettings.setFileInfo(fileInfo);

SignBarcodeOptions barcodeOptions = new SignBarcodeOptions();
barcodeOptions.setSignatureType(SignatureTypeEnum.BARCODE);

// set signature properties
barcodeOptions.setText("123456789012");
barcodeOptions.setBarcodeType("Code128");
barcodeOptions.setCodeTextAlignment(CodeTextAlignmentEnum.NONE);

// set signature position on a page
barcodeOptions.setLeft(100);
barcodeOptions.setTop(100);
barcodeOptions.setWidth(300);
barcodeOptions.setHeight(100);
barcodeOptions.setLocationMeasureType(LocationMeasureTypeEnum.PIXELS);
barcodeOptions.setSizeMeasureType(SizeMeasureTypeEnum.PIXELS);
barcodeOptions.setStretch(StretchEnum.NONE);
barcodeOptions.setRotationAngle(0);
barcodeOptions.setHorizontalAlignment(HorizontalAlignmentEnum.NONE);
barcodeOptions.setVerticalAlignment(VerticalAlignmentEnum.NONE);

Padding padding = new Padding();
padding.setAll(5);
barcodeOptions.setMargin(padding);
barcodeOptions.setMarginMeasureType(MarginMeasureTypeEnum.PIXELS);

Color backgroundColor = new Color();
backgroundColor.setWeb("DarkOrange");
barcodeOptions.setBackgroundColor(backgroundColor);

Padding innerMargins = new Padding();
innerMargins.setAll(2);
barcodeOptions.setInnerMargins(innerMargins);

*set pages for signing (each of these page settings could be used singly)
barcodeOptions.setPage(1);
barcodeOptions.setAllPages(true);

PagesSetup pagesSetup = new PagesSetup();
pagesSetup.setEvenPages(false);
pagesSetup.setFirstPage(true);
pagesSetup.setLastPage(false);
pagesSetup.setOddPages(false);
pagesSetup.addPageNumbersItem(1);
barcodeOptions.setPagesSetup(pagesSetup);
barcodeOptions.setTop(0);

SignTextOptions textOptions = new SignTextOptions();
textOptions.setSignatureType(SignatureTypeEnum.TEXT);

// set signature properties
textOptions.setText("John Smith");

// set signature position on a page
textOptions.setLeft(100);
textOptions.setTop(100);
textOptions.setWidth(100);
textOptions.setHeight(100);
textOptions.setLocationMeasureType(LocationMeasureTypeEnum.PIXELS);
textOptions.setSizeMeasureType(SizeMeasureTypeEnum.PIXELS);
textOptions.setStretch(StretchEnum.NONE);
textOptions.setRotationAngle(0);
textOptions.setHorizontalAlignment(HorizontalAlignmentEnum.NONE);
textOptions.setVerticalAlignment(VerticalAlignmentEnum.NONE);

padding = new Padding();
padding.setAll(5);
textOptions.setMargin(padding);
textOptions.setMarginMeasureType(MarginMeasureTypeEnum.PIXELS);

backgroundColor = new Color();
backgroundColor.setWeb("DarkOrange");
textOptions.setBackgroundColor(backgroundColor);

*set pages for signing (each of these page settings could be used singly)
textOptions.setPage(1);
textOptions.setAllPages(true);

pagesSetup = new PagesSetup();
pagesSetup.setEvenPages(false);
pagesSetup.setFirstPage(true);
pagesSetup.setLastPage(false);
pagesSetup.setOddPages(false);
pagesSetup.addPageNumbersItem(1);
textOptions.setPagesSetup(pagesSetup);

SaveOptions saveOptions = new SaveOptions();
saveOptions.setOutputFilePath("Signaturedocs\\signedCollectionOne_page.docx");

SignSettings signSettings = new SignSettings();
signSettings.setFileInfo(fileInfo);
signSettings.addOptionsItem(barcodeOptions);
signSettings.addOptionsItem(textOptions);
signSettings.setSaveOptions(saveOptions);

CreateSignaturesRequest request = new CreateSignaturesRequest(signSettings);

SignResult response = apiInstance.createSignatures(request);

```

{{< /tab >}} {{< tab tabNum="3" >}}

```php

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-php-samples
use GroupDocs\Signature\Model;
use GroupDocs\Signature\Model\Requests;

$ClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$ClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

$configuration = new GroupDocs\Signature\Configuration();
$configuration->setAppSid($ClientId);
$configuration->setAppKey($ClientSecret);

$apiInstance = new GroupDocs\Signature\SignApi($configuration);

$fileInfo = new GroupDocs\Signature\Model\FileInfo();
$fileInfo->setFilePath("signaturedocs\one-page.docx");

$settings = new GroupDocs\Signature\Model\SignSettings();
$settings->setFileInfo($fileInfo);

$saveOptions = new GroupDocs\Signature\Model\SaveOptions();
$saveOptions->setOutputFilePath("signaturedocs\signedCollectionsOne_page.docx");
$settings->setSaveOptions($saveOptions);

// Sign Text options
$textOptions = new GroupDocs\Signature\Model\SignTextOptions();
$textOptions->setPage(1);
$textOptions->setAllPages(false);
$textOptions->setSignatureType(GroupDocs\Signature\Model\OptionsBase::SIGNATURE_TYPE_TEXT);
$textOptions->setText("GroupDocs Cloud");
$textOptions->setLeft(100);
$textOptions->setTop(100);
$textOptions->setWidth(100);
$textOptions->setHeight(100);
$textOptions->setLocationMeasureType(GroupDocs\Signature\Model\SignTextOptions::LOCATION_MEASURE_TYPE_PIXELS);
$textOptions->setSizeMeasureType(GroupDocs\Signature\Model\SignTextOptions::SIZE_MEASURE_TYPE_PIXELS);
$textOptions->setStretch(GroupDocs\Signature\Model\SignTextOptions::STRETCH_NONE);
$textOptions->setRotationAngle(0);
$textOptions->setHorizontalAlignment(GroupDocs\Signature\Model\SignTextOptions::HORIZONTAL_ALIGNMENT_NONE);
$textOptions->setVerticalAlignment(GroupDocs\Signature\Model\SignTextOptions::VERTICAL_ALIGNMENT_NONE);

$padding = new GroupDocs\Signature\Model\Padding();
$padding->setAll(5);
$textOptions->setMargin($padding);
$textOptions->setMarginMeasureType(GroupDocs\Signature\Model\SignTextOptions::MARGIN_MEASURE_TYPE_PIXELS);
$color = new GroupDocs\Signature\Model\Color();
$color->setWeb("BlueViolet");
$textOptions->setForeColor($color);
$color = new GroupDocs\Signature\Model\Color();
$color->setWeb("DarkOrange");
$textOptions->setBackgroundColor($color);

$pagesSetup = new GroupDocs\Signature\Model\PagesSetup();
$pagesSetup->setEvenPages(false);
$pagesSetup->setFirstPage(true);
$pagesSetup->setLastPage(false);
$pagesSetup->setOddPages(false);
$pagesSetup->setPageNumbers([1]);
$textOptions->setPagesSetup($pagesSetup);

// Sign Barcode options
$barcodeOptions = new GroupDocs\Signature\Model\SignBarcodeOptions();
$barcodeOptions->setPage(1);
$barcodeOptions->setAllPages(false);
$barcodeOptions->setSignatureType(GroupDocs\Signature\Model\OptionsBase::SIGNATURE_TYPE_BARCODE);
$barcodeOptions->setBarcodeType("Code128");
$barcodeOptions->setText("123456789012");
$barcodeOptions->setCodeTextAlignment(GroupDocs\Signature\Model\SignBarcodeOptions::CODE_TEXT_ALIGNMENT_NONE);
$barcodeOptions->setLeft(100);
$barcodeOptions->setTop(100);
$barcodeOptions->setWidth(300);
$barcodeOptions->setHeight(100);
$barcodeOptions->setLocationMeasureType(GroupDocs\Signature\Model\SignTextOptions::LOCATION_MEASURE_TYPE_PIXELS);
$barcodeOptions->setSizeMeasureType(GroupDocs\Signature\Model\SignTextOptions::SIZE_MEASURE_TYPE_PIXELS);
$barcodeOptions->setStretch(GroupDocs\Signature\Model\SignTextOptions::STRETCH_NONE);
$barcodeOptions->setRotationAngle(0);
$barcodeOptions->setHorizontalAlignment(GroupDocs\Signature\Model\SignTextOptions::HORIZONTAL_ALIGNMENT_NONE);
$barcodeOptions->setVerticalAlignment(GroupDocs\Signature\Model\SignTextOptions::VERTICAL_ALIGNMENT_NONE);

$padding = new GroupDocs\Signature\Model\Padding();
$padding->setAll(5);
$barcodeOptions->setMargin($padding);

$barcodeOptions->setMarginMeasureType(GroupDocs\Signature\Model\SignTextOptions::MARGIN_MEASURE_TYPE_PIXELS);
$padding = new GroupDocs\Signature\Model\Padding();
$padding->setAll(2);
$barcodeOptions->setInnerMargins($padding);

$pagesSetup = new GroupDocs\Signature\Model\PagesSetup();
$pagesSetup->setEvenPages(false);
$pagesSetup->setFirstPage(true);
$pagesSetup->setLastPage(false);
$pagesSetup->setOddPages(false);
$pagesSetup->setPageNumbers([1]);
$barcodeOptions->setPagesSetup($pagesSetup);

$settings->setOptions([$textOptions, $barcodeOptions]);

$request = new GroupDocs\Signature\Model\Requests\createSignaturesRequest($settings);
$response = $apiInstance->createSignatures($request);

```

{{< /tab >}} {{< tab tabNum="4" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-node-samples
global.signature_cloud = require("groupdocs-signature-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

global.signApi = signature_cloud.SignApi.fromKeys(clientId, clientSecret);

let fileInfo = new signature_cloud.FileInfo();
fileInfo.filePath = "signaturedocs/one-page.docx";

let BarcodeOpts = new signature_cloud.SignBarcodeOptions();
BarcodeOpts.signatureType = signature_cloud.OptionsBase.SignatureTypeEnum.Barcode;
BarcodeOpts.barcodeType = 'Code39Standard';
BarcodeOpts.text = '123456789012';
BarcodeOpts.codeTextAlignment = signature_cloud.SignBarcodeOptions.CodeTextAlignmentEnum.None;

// set signature position on a page
BarcodeOpts.left = 100;
BarcodeOpts.top = 100;
BarcodeOpts.width = 300;
BarcodeOpts.height = 100;
BarcodeOpts.locationMeasureType = signature_cloud.SignTextOptions.LocationMeasureTypeEnum.Pixels;
BarcodeOpts.sizeMeasureType = signature_cloud.SignTextOptions.SizeMeasureTypeEnum.Pixels;
BarcodeOpts.stretch = signature_cloud.SignTextOptions.StretchEnum.None;
BarcodeOpts.rotationAngle = 0;
BarcodeOpts.horizontalAlignment = signature_cloud.SignTextOptions.HorizontalAlignmentEnum.None;
BarcodeOpts.verticalAlignment = signature_cloud.SignTextOptions.VerticalAlignmentEnum.None;

BarcodeOpts.margin = new signature_cloud.Padding();
BarcodeOpts.margin.all = 5;
BarcodeOpts.marginMeasureType = signature_cloud.SignTextOptions.MarginMeasureTypeEnum.Pixels;

// set signature appearance
BarcodeOpts.foreColor = new signature_cloud.Color();
BarcodeOpts.foreColor.web = "BlueViolet";

BarcodeOpts.backgroundColor = new signature_cloud.Color();
BarcodeOpts.backgroundColor.web = "DarkOrange";

BarcodeOpts.innerMargins = new signature_cloud.Padding();
BarcodeOpts.innerMargins.all = 2;

BarcodeOpts.page = 1;
BarcodeOpts.allPages = false;

let TextOpts = new signature_cloud.SignTextOptions();
TextOpts.signatureType = signature_cloud.OptionsBase.SignatureTypeEnum.Text;
TextOpts.text = 'GroupDocs.Signature Cloud';

// set signature position on a page
TextOpts.left = 100;
TextOpts.top = 100;
TextOpts.width = 100;
TextOpts.height = 100;
TextOpts.locationMeasureType = signature_cloud.SignTextOptions.LocationMeasureTypeEnum.Pixels;
TextOpts.sizeMeasureType = signature_cloud.SignTextOptions.SizeMeasureTypeEnum.Pixels;
TextOpts.stretch = signature_cloud.SignTextOptions.StretchEnum.None;
TextOpts.rotationAngle = 0;
TextOpts.horizontalAlignment = signature_cloud.SignTextOptions.HorizontalAlignmentEnum.None;
TextOpts.verticalAlignment = signature_cloud.SignTextOptions.VerticalAlignmentEnum.None;

TextOpts.margin = new signature_cloud.Padding();
TextOpts.margin.all = 5;
TextOpts.marginMeasureType = signature_cloud.SignTextOptions.MarginMeasureTypeEnum.Pixels;

// set signature appearance
TextOpts.font = new signature_cloud.SignatureFont();
TextOpts.font.fontFamily = "Arial";
TextOpts.font.fontSize = 12;
TextOpts.font.bold = true;
TextOpts.font.italic = false;
TextOpts.font.underline = false;

TextOpts.foreColor = new signature_cloud.Color();
TextOpts.foreColor.web = "BlueViolet";

TextOpts.backgroundColor = new signature_cloud.Color();
TextOpts.backgroundColor.web = "DarkOrange";
TextOpts.page = 1;
TextOpts.allPages = false;

let settings = new signature_cloud.SignSettings();
settings.fileInfo = fileInfo;
settings.options = [BarcodeOpts, TextOpts];
settings.saveOptions = new signature_cloud.SaveOptions();
settings.saveOptions.outputFilePath = "signaturedocs/signedCollection_One_page.docx";

let request = new signature_cloud.CreateSignaturesRequest(settings);
let response = await signApi.createSignatures(request);

```

{{< /tab >}} {{< tab tabNum="5" >}}

```python

# For complete examples and data files, please go to https://github.com/groupdocs-signature_cloud-cloud/groupdocs-signature_cloud-cloud-python-samples
from groupdocs_signature_cloud import *
import groupdocs_signature_cloud

client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

api = groupdocs_signature_cloud.SignApi.from_keys(client_id, client_secret)

fileInfo = FileInfo()
fileInfo.file_path = "signaturedocs\\one-page.docx"

Barcodeopts = SignBarcodeOptions()
Barcodeopts.signature_type = 'Barcode'
Barcodeopts.text = '123456789012'
Barcodeopts.barcode_type = 'Code128'
Barcodeopts.code_text_alignment = 'None'

# set signature position on a page
Barcodeopts.left = 100
Barcodeopts.top = 100
Barcodeopts.width = 300
Barcodeopts.height = 100
Barcodeopts.location_measure_type = "Pixels"
Barcodeopts.size_measure_type = "Pixels"
Barcodeopts.stretch = "None"
Barcodeopts.rotation_angle = 0
Barcodeopts.horizontal_alignment = "None"
Barcodeopts.vertical_alignment = "None"
Barcodeopts.margin = Padding()
Barcodeopts.margin.all = 5
Barcodeopts.margin_measure_type = "Pixels"

# set signature appearance
Barcodeopts.fore_color = Color()
Barcodeopts.fore_color.web = "BlueViolet"
Barcodeopts.background_color = Color()
Barcodeopts.background_color.web = "DarkOrange"
Barcodeopts.inner_margins = Padding()
Barcodeopts.inner_margins.all = 2

Barcodeopts.page = 1

QRCodeopts = SignQRCodeOptions()
QRCodeopts.signature_type = 'QRCode'
QRCodeopts.text = 'GroupDocs.Signature Cloud'
QRCodeopts.qr_code_type = 'Aztec'

# set signature position on a page
QRCodeopts.left = 100
QRCodeopts.top = 100
QRCodeopts.width = 200
QRCodeopts.height = 100
QRCodeopts.location_measure_type = "Pixels"
QRCodeopts.size_measure_type = "Pixels"
QRCodeopts.stretch = "None"
QRCodeopts.rotation_angle = 0
QRCodeopts.horizontal_alignment = "None"
QRCodeopts.vertical_alignment = "None"
QRCodeopts.margin = Padding()
QRCodeopts.margin.all = 5
QRCodeopts.margin_measure_type = "Pixels"

# set signature appearance
QRCodeopts.fore_color = Color()
QRCodeopts.fore_color.web = "BlueViolet"
QRCodeopts.background_color = Color()
QRCodeopts.background_color.web = "DarkOrange"
QRCodeopts.inner_margins = Padding()
QRCodeopts.inner_margins.all = 2

QRCodeopts.page = 1
QRCodeopts.all_pages = False
ps = PagesSetup()
ps.even_pages = False
ps.first_page = True
ps.last_page = False
ps.odd_pages = False
ps.page_numbers = [1]
QRCodeopts.pages_setup = ps

settings = SignSettings()
settings.options = [Barcodeopts,QRCodeopts]

settings.save_options = SaveOptions()
settings.save_options.output_file_path = "signaturedocs\\signedCollectionOne_page.docx"
settings.file_info = fileInfo

request = CreateSignaturesRequest(settings)
response = api.create_signatures(request)

```

{{< /tab >}} {{< tab tabNum="6" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-ruby-samples
require 'groupdocs_signature_cloud'

$client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

api = GroupDocsSignatureCloud::SignApi.from_keys($client_id, $client_secret)

$info = GroupDocsSignatureCloud::FileInfo.new()
$info.file_path = "signaturedocs\\one-page.docx"

$BarcodeOpts = GroupDocsSignatureCloud::SignBarcodeOptions.new()
$BarcodeOpts.signature_type = 'Barcode'
$BarcodeOpts.barcode_type = 'Code128'
$BarcodeOpts.text = '123456789012'
$BarcodeOpts.code_text_alignment = 'None'

# set signature position on a page
$BarcodeOpts.left = 100
$BarcodeOpts.top = 100
$BarcodeOpts.width = 300
$BarcodeOpts.height = 100
$BarcodeOpts.location_measure_type = "Pixels"
$BarcodeOpts.size_measure_type = "Pixels"
$BarcodeOpts.stretch = "None"
$BarcodeOpts.rotation_angle = 0
$BarcodeOpts.horizontal_alignment = "None"
$BarcodeOpts.vertical_alignment = "None"

$BarcodeOpts.margin = GroupDocsSignatureCloud::Padding.new()
$BarcodeOpts.margin.all = 5
$BarcodeOpts.margin_measure_type = "Pixels"

# set signature appearance
$BarcodeOpts.fore_color = GroupDocsSignatureCloud::Color.new()
$BarcodeOpts.fore_color.web = "BlueViolet"

$BarcodeOpts.background_color = GroupDocsSignatureCloud::Color.new()
$BarcodeOpts.background_color.web = "DarkOrange"

$BarcodeOpts.inner_margins = GroupDocsSignatureCloud::Padding.new()
$BarcodeOpts.inner_margins.all = 2

$BarcodeOpts.page = 1

$QRCodeOpts = GroupDocsSignatureCloud::SignQRCodeOptions.new()
$QRCodeOpts.signature_type = 'QRCode'
$QRCodeOpts.text = 'John Smit'
$QRCodeOpts.qr_code_type = 'Aztec'

# set signature position on a page
$QRCodeOpts.left = 100
$QRCodeOpts.top = 100
$QRCodeOpts.width = 200
$QRCodeOpts.height = 100
$QRCodeOpts.location_measure_type = "Pixels"
$QRCodeOpts.size_measure_type = "Pixels"
$QRCodeOpts.stretch = "None"
$QRCodeOpts.rotation_angle = 0
$QRCodeOpts.horizontal_alignment = "None"
$QRCodeOpts.vertical_alignment = "None"

$QRCodeOpts.margin = GroupDocsSignatureCloud::Padding.new()
$QRCodeOpts.margin.all = 5
$QRCodeOpts.margin_measure_type = "Pixels"

# set signature appearance
$QRCodeOpts.fore_color = GroupDocsSignatureCloud::Color.new()
$QRCodeOpts.fore_color.web = "BlueViolet"

$QRCodeOpts.background_color = GroupDocsSignatureCloud::Color.new()
$QRCodeOpts.background_color.web = "DarkOrange"

$QRCodeOpts.inner_margins = GroupDocsSignatureCloud::Padding.new()
$QRCodeOpts.inner_margins.all = 2

$QRCodeOpts.page = 1

$settings = GroupDocsSignatureCloud::SignSettings.new()
$settings.options = [$BarcodeOpts, $QRCodeOpts]

$settings.save_options = GroupDocsSignatureCloud::SaveOptions.new()
$settings.save_options.output_file_path = "signaturedocs\\signedCollectionOne_page.docx"

$settings.file_info = $info
$request = GroupDocsSignatureCloud::CreateSignaturesRequest.new($settings)

# Executing an API.
$response = api.create_signatures($request)

```

{{< /tab >}} {{< /tabs >}}

