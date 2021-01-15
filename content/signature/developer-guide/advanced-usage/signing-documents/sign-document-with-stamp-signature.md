---
id: "sign-document-with-stamp-signature"
url: "signature/sign-document-with-stamp-signature"
title: "Sign document with stamp signature"
productName: "GroupDocs.Signature Cloud"
description: ""
keywords: ""
---

# Introduction #

A **stamp** signature is a special type of electronic signature that have visual appearance of round seal and its visual parameters can be set programmatically.
Every stamp signature can have multiple "stamp lines" with custom text and different line thickness, color, font weight and size. Here is an example of how stamp signature created with GroupDocs.Siganture Cloud may look like:

![stamp](signature/images/Stamp.png)

GroupDocs.Signature Cloud provides options to specify different options for Stamp signature:

* Stamp type - Round or Square;
* Height and width in pixels;
* Alignment and position within the document page;
* and many more.

Each Stamp option contains inner and outer lines. Inner lines represent vertical lines inside the stamp, when outer lines represent circles (or rectangles based on stamp type) around stamp with own text, border settings, background etc.

## API Usage ##

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
    'FilePath': 'signaturedocs/one-page.docx'
  },
  'Options': [
    {
      'SignatureType': 'Stamp',
      'ImageFilePath': 'signaturedocs/signature.jpg',
      'Left': 100,
      'Top': 100,
      'Width': 300,
      'Height': 200,
      'RotationAngle': 0,
      'Page': 1,
      'OuterLines': [
        {
          'BackgroundColor': {
            'Web': 'BlueViolet'
          },
          'Text': 'John Smith',
          'Visible': true
        }
      ],
      'InnerLines': [
        {
          'BackgroundColor': {
            'Web': 'CornflowerBlue'
          },
          'Text': 'John Smith',
          'Visible': true
        }
      ]
    }
  ],
  'SaveOptions': {
    'OutputFilePath': 'signaturedocs/signedStamp_one-page.docx'
  }
}"

```

{{< /tab >}} {{< tab tabNum="2" >}}

```javascript

{
  "fileInfo": {
    "filePath": "signaturedocs/signedStamp_one-page.docx",
    "storageName": null,
    "versionId": null,
    "password": null
  },
  "size": 1365482,
  "downloadUrl": "https://api-qa.groupdocs.cloud/v2.0/signature/storage/file/signaturedocs/signedStamp_one-page.docx",
  "succeeded": [
    {
      "size": 0,
      "format": null,
      "signatureType": "Image",
      "pageNumber": 1,
      "signatureId": "54be6c48-4e02-4560-a2d3-1c0375fb51da",
      "isSignature": true,
      "createdOn": "2020-07-21T11:52:24.7993457+00:00",
      "modifiedOn": "2020-07-21T11:52:24.7993457+00:00",
      "top": 100,
      "left": 100,
      "width": 300,
      "height": 200
    }
  ],
  "failed": []
}

{{< /tab >}} {{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](signature/available-sdks).

### SDK Examples ###

{{< tabs tabTotal="6" tabID="10" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Python" tabName6="Ruby" >}} {{< tab tabNum="1" >}}

```csharp

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-dotnet-samples
string MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
string MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

var configuration = new Configuration(MyClientId, MyClientSecret);
var apiInstance = new SignApi(configuration);

// Sign options
var options = new SignStampOptions
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
// Sign settings
var signSettings = new SignSettings
{
    FileInfo = new FileInfo
    {
        FilePath = "one-page.docx"
    },
    SaveOptions = new SaveOptions { OutputFilePath = "signedStamp_one-page.docx", SaveFormat = "docx" },
    Options = new List<SignOptions> { options }
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

SignStampOptions options = new SignStampOptions();
options.setSignatureType(SignatureTypeEnum.STAMP);

Color cornflowerBlueColor = new Color();
cornflowerBlueColor.setWeb("CornflowerBlue");

Color goldColor = new Color();
goldColor.setWeb("Gold");

Color blueVioletColor = new Color();
blueVioletColor.setWeb("BlueViolet");

Color darkOrangeColor = new Color();
darkOrangeColor.setWeb("DarkOrange");

Color oliveDrabColor = new Color();
oliveDrabColor.setWeb("OliveDrab");

Color ghostWhiteColor = new Color();
ghostWhiteColor.setWeb("GhostWhite");

// set signature properties
options.setImageFilePath("Signaturedocs\\signature.jpg");

// set signature position on a page
options.setLeft(100);
options.setTop(100);
options.setWidth(300);
options.setHeight(200);
options.setLocationMeasureType(LocationMeasureTypeEnum.PIXELS);
options.setSizeMeasureType(SizeMeasureTypeEnum.PIXELS);
options.setRotationAngle(0);
options.setHorizontalAlignment(HorizontalAlignmentEnum.NONE);
options.setVerticalAlignment(VerticalAlignmentEnum.NONE);

Padding padding = new Padding();
padding.setAll(5);
options.setMargin(padding);
options.setMarginMeasureType(MarginMeasureTypeEnum.PIXELS);

// set signature appearance
options.setBackgroundColor(cornflowerBlueColor);
options.setBackgroundColorCropType(SignStampOptions.BackgroundColorCropTypeEnum.INNERAREA);
options.setBackgroundImageCropType(SignStampOptions.BackgroundImageCropTypeEnum.MIDDLEAREA);

*Outer line
StampLine outerLine = new StampLine();
outerLine.setText("John Smith");

SignatureFont outerLineFont = new SignatureFont();
outerLineFont.setFontFamily("Arial");
outerLineFont.setFontSize(12.0);
outerLineFont.setBold(true);
outerLineFont.setItalic(true);
outerLineFont.setUnderline(true);
outerLine.setFont(outerLineFont);
outerLine.setTextBottomIntent(5);
outerLine.setTextColor(goldColor);
outerLine.setTextRepeatType(StampLine.TextRepeatTypeEnum.FULLTEXTREPEAT);
outerLine.setBackgroundColor(blueVioletColor);
outerLine.setHeight(20);

BorderLine outerLineInnerBorder = new BorderLine();
outerLineInnerBorder.setColor(darkOrangeColor);
outerLineInnerBorder.setStyle(BorderLine.StyleEnum.LONGDASH);
outerLineInnerBorder.setTransparency(0.5);
outerLineInnerBorder.setWeight(1.2);
outerLine.setInnerBorder(outerLineInnerBorder);

BorderLine outerLineOuterBorder = new BorderLine();
outerLineOuterBorder.setColor(darkOrangeColor);
outerLineOuterBorder.setStyle(BorderLine.StyleEnum.LONGDASHDOT);
outerLineOuterBorder.setTransparency(0.7);
outerLineOuterBorder.setWeight(1.4);
outerLine.setOuterBorder(outerLineOuterBorder);

outerLine.setVisible(true);
options.addOuterLinesItem(outerLine);

*Inner line
StampLine innerLine = new StampLine();
innerLine.setText("John Smith");

SignatureFont innerLineFont = new SignatureFont();
innerLineFont.setFontFamily("Times New Roman");
innerLineFont.setFontSize(20.0);
innerLineFont.setBold(true);
innerLineFont.setItalic(true);
innerLineFont.setUnderline(true);
innerLine.setFont(innerLineFont);
innerLine.setTextBottomIntent(3);
innerLine.setTextColor(goldColor);
innerLine.setTextRepeatType(StampLine.TextRepeatTypeEnum.NONE);
innerLine.setBackgroundColor(cornflowerBlueColor);
innerLine.setHeight(30);

BorderLine innerLineInnerBorder = new BorderLine();
innerLineInnerBorder.setColor(oliveDrabColor);
innerLineInnerBorder.setStyle(BorderLine.StyleEnum.LONGDASH);
innerLineInnerBorder.setTransparency(0.5);
innerLineInnerBorder.setWeight(1.2);
innerLine.setInnerBorder(innerLineInnerBorder);

BorderLine innerLineOuterBorder = new BorderLine();
innerLineOuterBorder.setColor(ghostWhiteColor);
innerLineOuterBorder.setStyle(BorderLine.StyleEnum.DOT);
innerLineOuterBorder.setTransparency(0.4);
innerLineOuterBorder.setWeight(1.4);
innerLine.setOuterBorder(innerLineOuterBorder);

innerLine.setVisible(true);
options.addInnerLinesItem(innerLine);

*set pages for signing (each of these page settings could be used singly)
options.setPage(1);
options.setAllPages(true);

PagesSetup pagesSetup = new PagesSetup();
pagesSetup.setEvenPages(false);
pagesSetup.setFirstPage(true);
pagesSetup.setLastPage(false);
pagesSetup.setOddPages(false);
pagesSetup.addPageNumbersItem(1);
options.setPagesSetup(pagesSetup);

SaveOptions saveOptions = new SaveOptions();
saveOptions.setOutputFilePath("Signaturedocs\\signedStamp_one-page.docx");

SignSettings signSettings = new SignSettings();
signSettings.setFileInfo(fileInfo);
signSettings.addOptionsItem(options);
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
$fileInfo->setPassword("");

$settings = new GroupDocs\Signature\Model\SignSettings();
$settings->setFileInfo($fileInfo);

$saveOptions = new GroupDocs\Signature\Model\SaveOptions();
$saveOptions->setOutputFilePath("signaturedocs\signedStampOne_page.docx");
$settings->setSaveOptions($saveOptions);

$options = new GroupDocs\Signature\Model\SignStampOptions();
$options->setPage(1);
$options->setAllPages(false);
$options->setSignatureType(GroupDocs\Signature\Model\OptionsBase::SIGNATURE_TYPE_STAMP);
$options->setImageFilePath("signaturedocs\signature.jpg");
$options->setLeft(100);
$options->setTop(100);
$options->setWidth(300);
$options->setHeight(100);
$options->setLocationMeasureType(GroupDocs\Signature\Model\SignTextOptions::LOCATION_MEASURE_TYPE_PIXELS);
$options->setSizeMeasureType(GroupDocs\Signature\Model\SignTextOptions::SIZE_MEASURE_TYPE_PIXELS);
$options->setRotationAngle(0);
$options->setHorizontalAlignment(GroupDocs\Signature\Model\SignTextOptions::HORIZONTAL_ALIGNMENT_NONE);
$options->setVerticalAlignment(GroupDocs\Signature\Model\SignTextOptions::VERTICAL_ALIGNMENT_NONE);

$padding = new GroupDocs\Signature\Model\Padding();
$padding->setAll(5);
$options->setMargin($padding);
$options->setMarginMeasureType(GroupDocs\Signature\Model\SignTextOptions::MARGIN_MEASURE_TYPE_PIXELS);
$color = new GroupDocs\Signature\Model\Color();
$color->setWeb("CornflowerBlue");
$options->setBackgroundColor($color);
$options->setBackgroundColorCropType(GroupDocs\Signature\Model\SignStampOptions::BACKGROUND_COLOR_CROP_TYPE_INNER_AREA);
$options->setBackgroundImageCropType(GroupDocs\Signature\Model\SignStampOptions::BACKGROUND_IMAGE_CROP_TYPE_MIDDLE_AREA);

$stampLine = new GroupDocs\Signature\Model\StampLine();
$stampLine->setText("John Smith");
$stampLine->setTextBottomIntent(5);
$stampLine->setTextRepeatType(GroupDocs\Signature\Model\StampLine::TEXT_REPEAT_TYPE_FULL_TEXT_REPEAT);
$color = new GroupDocs\Signature\Model\Color();
$color->setWeb("Gold");
$stampLine->setTextColor($color);
$stampLine->setHeight(30);
$stampLine->setVisible(true);
$options->setOuterLines([$stampLine]);

$stampLine = new GroupDocs\Signature\Model\StampLine();
$stampLine->setText("John Smith");
$stampLine->setTextBottomIntent(3);
$stampLine->setTextRepeatType(GroupDocs\Signature\Model\StampLine::TEXT_REPEAT_TYPE_NONE);
$color = new GroupDocs\Signature\Model\Color();
$color->setWeb("Gold");
$stampLine->setTextColor($color);
$stampLine->setHeight(30);
$stampLine->setVisible(true);
$options->setInnerLines([$stampLine]);

$pagesSetup = new GroupDocs\Signature\Model\PagesSetup();
$pagesSetup->setEvenPages(false);
$pagesSetup->setFirstPage(true);
$pagesSetup->setLastPage(false);
$pagesSetup->setOddPages(false);
$pagesSetup->setPageNumbers([1]);
$options->setPagesSetup($pagesSetup);

$settings->setOptions([$options]);

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

let opts = new signature_cloud.SignStampOptions();
opts.signatureType = signature_cloud.OptionsBase.SignatureTypeEnum.Stamp;
opts.imageFilePath = "signaturedocs/signature.jpg";

// set signature position on a page
opts.left = 100;
opts.top = 100;
opts.width = 300;
opts.height = 200;
opts.locationMeasureType = signature_cloud.SignTextOptions.LocationMeasureTypeEnum.Pixels;
opts.sizeMeasureType = signature_cloud.SignTextOptions.SizeMeasureTypeEnum.Pixels;
opts.rotationAngle = 0;
opts.horizontalAlignment = signature_cloud.SignTextOptions.HorizontalAlignmentEnum.None;
opts.verticalAlignment = signature_cloud.SignTextOptions.VerticalAlignmentEnum.None;

opts.margin = new signature_cloud.Padding();
opts.margin.all = 5;
opts.marginMeasureType = signature_cloud.SignTextOptions.MarginMeasureTypeEnum.Pixels;

// set signature appearance
opts.backgroundColor = new signature_cloud.Color();
opts.backgroundColor.web = "CornflowerBlue";
opts.backgroundColorCropType = signature_cloud.SignStampOptions.BackgroundColorCropTypeEnum.InnerArea;
opts.backgroundImageCropType = signature_cloud.SignStampOptions.BackgroundImageCropTypeEnum.MiddleArea;

let outline = new signature_cloud.StampLine();
outline.text = "GroupDocs";

outline.font = new signature_cloud.SignatureFont();
outline.font.fontFamily = "Arial";
outline.font.fontSize = 12;
outline.font.bold = true;
outline.font.italic = true;
outline.font.underline = true;
outline.textBottomIntent = 5;

outline.textColor = new signature_cloud.Color();
outline.textColor.web = "Gold";
outline.textRepeatType = signature_cloud.StampLine.TextRepeatTypeEnum.FullTextRepeat;

outline.backgroundColor = new signature_cloud.Color();
outline.backgroundColor.web = "BlueViolet";
outline.height = 20;

outline.innerBorder = new signature_cloud.BorderLine();
outline.innerBorder.color = new signature_cloud.Color();
outline.innerBorder.color.web = "DarkOrange";
outline.innerBorder.style = signature_cloud.BorderLine.StyleEnum.LongDash;
outline.innerBorder.transparency = 0.5;
outline.innerBorder.weight = 1.2;

outline.outerBorder = new signature_cloud.BorderLine();
outline.outerBorder.color = new signature_cloud.Color();
outline.outerBorder.color.web = "DarkOrange";
outline.outerBorder.style = signature_cloud.BorderLine.StyleEnum.LongDashDot;
outline.outerBorder.transparency = 0.7;
outline.outerBorder.weight = 1.4;
outline.visible = true;
opts.outerLines = [outline];

let innerline = new signature_cloud.StampLine();
innerline.text = "GroupDocs.Signature Cloud";

innerline.font = new signature_cloud.SignatureFont();
innerline.font.fontFamily = "Times New Roman";
innerline.font.fontSize = 20;
innerline.font.bold = true;
innerline.font.italic = true;
innerline.font.underline = true;
innerline.textBottomIntent = 3;

innerline.textColor = new signature_cloud.Color();
innerline.textColor.web = "Gold";
innerline.textRepeatType = signature_cloud.StampLine.TextRepeatTypeEnum.None;

innerline.backgroundColor = new signature_cloud.Color();
innerline.backgroundColor.web = "CornflowerBlue";
innerline.height = 30;

innerline.innerBorder = new signature_cloud.BorderLine();
innerline.innerBorder.color = new signature_cloud.Color();
innerline.innerBorder.color.web = "OliveDrab";
innerline.innerBorder.style = signature_cloud.BorderLine.StyleEnum.LongDash;
innerline.innerBorder.transparency = 0.5;
innerline.innerBorder.weight = 1.2;

innerline.outerBorder = new signature_cloud.BorderLine();
innerline.outerBorder.color = new signature_cloud.Color();
innerline.outerBorder.color.web = "GhostWhite";
innerline.outerBorder.style = signature_cloud.BorderLine.StyleEnum.LongDashDot;
innerline.outerBorder.transparency = 0.4;
innerline.outerBorder.weight = 1.4;
innerline.visible = true;
opts.innerLines = [innerline];

opts.page = 1;

let settings = new signature_cloud.SignSettings();
settings.fileInfo = fileInfo;
settings.options = [opts];
settings.saveOptions = new signature_cloud.SaveOptions();
settings.saveOptions.outputFilePath = "signaturedocs/signedStamp_One_page.docx";

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

opts = SignStampOptions()
opts.signature_type = 'Stamp'
opts.image_file_path = "signaturedocs\\signature.jpg"

# set signature position on a page
opts.left = 100
opts.top = 100
opts.width = 300
opts.height = 200
opts.location_measure_type = "Pixels"
opts.size_measure_type = "Pixels"
opts.rotation_angle = 0
opts.horizontal_alignment = "None"
opts.vertical_alignment = "None"
opts.margin = Padding()
opts.margin.all = 5
opts.margin_measure_type = "Pixels"

# set signature appearance
opts.background_color = Color()
opts.background_color.web = "CornflowerBlue"
opts.background_color_crop_type = "InnerArea"
opts.background_image_crop_type = "MiddleArea"

outline = StampLine()
outline.text = "John Smith"
outline.font = SignatureFont()
outline.font.font_family = "Arial"
outline.font.font_size = 12
outline.font.bold = True
outline.font.italic = True
outline.font.underline = True
outline.text_bottom_intent = 5
outline.text_color = Color()
outline.text_color.web = "Gold"
outline.text_repeat_type = "FullTextRepeat"
outline.background_color = Color()
outline.background_color.web = "BlueViolet"
outline.height = 20
outline.inner_border = BorderLine()
outline.inner_border.color = Color()
outline.inner_border.color.web = "DarkOrange"
outline.inner_border.style = "LongDash"
outline.inner_border.transparency = 0.5
outline.inner_border.weight = 1.2
outline.outer_border = BorderLine()
outline.outer_border.color = Color()
outline.outer_border.color.web = "DarkOrange"
outline.outer_border.style = "LongDashDot"
outline.outer_border.transparency = 0.7
outline.outer_border.weight = 1.4
outline.visible = True
opts.outer_lines = [outline]

innerline = StampLine()
innerline.text = "John Smith"
innerline.font = SignatureFont()
innerline.font.font_family = "Times New Roman"
innerline.font.font_size = 20
innerline.font.bold = True
innerline.font.italic = True
innerline.font.underline = True
innerline.text_bottom_intent = 3
innerline.text_color = Color()
innerline.text_color.web = "Gold"
innerline.text_repeat_type = "None"
innerline.background_color = Color()
innerline.background_color.web = "CornflowerBlue"
innerline.height = 30
innerline.inner_border = BorderLine()
innerline.inner_border.color = Color()
innerline.inner_border.color.web = "OliveDrab"
innerline.inner_border.style = "LongDash"
innerline.inner_border.transparency = 0.5
innerline.inner_border.weight = 1.2
innerline.outer_border = BorderLine()
innerline.outer_border.color = Color()
innerline.outer_border.color.web = "GhostWhite"
innerline.outer_border.style = "Dot"
innerline.outer_border.transparency = 0.4
innerline.outer_border.weight = 1.4
innerline.visible = True
opts.inner_lines = [innerline]

opts.page = 1

settings = SignSettings()
settings.options = [opts]

settings.save_options = SaveOptions()
settings.save_options.output_file_path = "signaturedocs\\signedStampOne_page.docx"
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

$opts = GroupDocsSignatureCloud::SignStampOptions.new()
$opts.signature_type = "Stamp"
$opts.image_file_path = "signaturedocs\\signature.jpg"

# set signature position on a page
$opts.left = 100
$opts.top = 100
$opts.width = 300
$opts.height = 200
$opts.location_measure_type = "Pixels"
$opts.size_measure_type = "Pixels"
$opts.rotation_angle = 0
$opts.horizontal_alignment = "None"
$opts.vertical_alignment = "None"

$opts.margin = GroupDocsSignatureCloud::Padding.new()
$opts.margin.all = 5
$opts.margin_measure_type = "Pixels"

# set signature appearance
$opts.background_color = GroupDocsSignatureCloud::Color.new()
$opts.background_color.web = "CornflowerBlue"
$opts.background_color_crop_type = "InnerArea"
$opts.background_image_crop_type = "MiddleArea"

$outline = GroupDocsSignatureCloud::StampLine.new()
$outline.text = "John Smith"

$outline.font = GroupDocsSignatureCloud::SignatureFont.new()
$outline.font.font_family = "Arial"
$outline.font.font_size = 12
$outline.font.bold = true
$outline.font.italic = true
$outline.font.underline = true
$outline.text_bottom_intent = 5

$outline.text_color = GroupDocsSignatureCloud::Color.new()
$outline.text_color.web = "Gold"
$outline.text_repeat_type = "FullTextRepeat"

$outline.background_color = GroupDocsSignatureCloud::Color.new()
$outline.background_color.web = "BlueViolet"
$outline.height = 20

$outline.inner_border = GroupDocsSignatureCloud::BorderLine.new()
$outline.inner_border.color = GroupDocsSignatureCloud::Color.new()
$outline.inner_border.color.web = "DarkOrange"
$outline.inner_border.style = "LongDash"
$outline.inner_border.transparency = 0.5
$outline.inner_border.weight = 1.2

$outline.outer_border = GroupDocsSignatureCloud::BorderLine.new()
$outline.outer_border.color = GroupDocsSignatureCloud::Color.new()
$outline.outer_border.color.web = "DarkOrange"
$outline.outer_border.style = "LongDashDot"
$outline.outer_border.transparency = 0.7
$outline.outer_border.weight = 1.4
$outline.visible = true
$opts.outer_lines = [$outline]

$innerline = GroupDocsSignatureCloud::StampLine.new()
$innerline.text = "John Smith"

$innerline.font = GroupDocsSignatureCloud::SignatureFont.new()
$innerline.font.font_family = "Times New Roman"
$innerline.font.font_size = 20
$innerline.font.bold = true
$innerline.font.italic = true
$innerline.font.underline = true
$innerline.text_bottom_intent = 3

$innerline.text_color = GroupDocsSignatureCloud::Color.new()
$innerline.text_color.web = "Gold"
$innerline.text_repeat_type = "None"

$innerline.background_color = GroupDocsSignatureCloud::Color.new()
$innerline.background_color.web = "CornflowerBlue"
$innerline.height = 30

$innerline.inner_border = GroupDocsSignatureCloud::BorderLine.new()
$innerline.inner_border.color = GroupDocsSignatureCloud::Color.new()
$innerline.inner_border.color.web = "OliveDrab"
$innerline.inner_border.style = "LongDash"
$innerline.inner_border.transparency = 0.5
$innerline.inner_border.weight = 1.2

$innerline.outer_border = GroupDocsSignatureCloud::BorderLine.new()
$innerline.outer_border.color = GroupDocsSignatureCloud::Color.new()
$innerline.outer_border.color.web = "GhostWhite"
$innerline.outer_border.style = "Dot"
$innerline.outer_border.transparency = 0.4
$innerline.outer_border.weight = 1.4
$innerline.visible = true
$opts.inner_lines = [$innerline]

$opts.page = 1

$settings = GroupDocsSignatureCloud::SignSettings.new()
$settings.options = [$opts]

$settings.save_options = GroupDocsSignatureCloud::SaveOptions.new()
$settings.save_options.output_file_path = "signaturedocs\\signedStampOne_page.docx"
$settings.file_info = $info

$request = GroupDocsSignatureCloud::CreateSignaturesRequest.new($settings)

# Executing an API.
$response = api.create_signatures($request)

```

{{< /tab >}} {{< /tabs >}}

