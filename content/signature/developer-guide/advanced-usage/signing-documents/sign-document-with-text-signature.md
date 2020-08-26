---
id: "sign-document-with-text-signature"
url: "signature/sign-document-with-text-signature"
title: "Sign document with text signature"
productName: "GroupDocs.Signature Cloud"
description: ""
keywords: ""
---

# Introduction #

A** Text** electronic signature is an arbitrary text that is added to a document in a native way dependent on document type. GroupDocs.Signature Cloud provides text signature feature and allows to customize wide range of text settings - from font name, size and color to alignment, borders, shadow effects etc. This is how text signature may look like: 

![text](signature/images/image2020-7-22_8_45_40.png)

To manipulate with text signatures GroupDocs.Signature Cloud provides various text sign options.

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
// Please get your App Key and App SID from https://dashboard.groupdocs.cloud/#/apps. Kindly place App Key in "client_secret" and App SID in "client_id" argument.
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
      'SignatureType': 'Text',
      'Text': 'GroupDocs.Signature Cloud',
      'Left': 100,
      'Top': 100,
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
  "size": 1352783,
  "downloadUrl": "https://api-qa.groupdocs.cloud/v2.0/signature/storage/file/signedText_one-page.docx",
  "succeeded": [
    {
      "text": "GroupDocs.Signature Cloud",
      "signatureImplementation": "Native",
      "signatureType": "Text",
      "pageNumber": 1,
      "signatureId": "ba2a7dcf-7d9b-488e-b12e-371a127feea9",
      "isSignature": true,
      "createdOn": "2020-07-22T06:11:21.6639488+00:00",
      "modifiedOn": "2020-07-22T06:11:21.6639488+00:00",
      "top": 100,
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

C#

```csharp

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-dotnet-samples
string MyAppKey = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
string MyAppSid = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud

var configuration = new Configuration(MyAppSid, MyAppKey);
var apiInstance = new SignApi(configuration);

// Sign options
var options = new SignTextOptions
{
    SignatureType = SignatureTypeEnum.Text,
    Text = "GroupDocs.Signature Cloud",
    Left = 100,
    Top = 100,
    Width = 100,
    Height = 100,
    LocationMeasureType = SignTextOptions.LocationMeasureTypeEnum.Pixels,
    SizeMeasureType = SignTextOptions.SizeMeasureTypeEnum.Pixels,
    Stretch = SignTextOptions.StretchEnum.None,
    RotationAngle = 0,
    HorizontalAlignment = SignTextOptions.HorizontalAlignmentEnum.None,
    VerticalAlignment = SignTextOptions.VerticalAlignmentEnum.None,
    Margin = new Padding {All = 5},
    MarginMeasureType = SignTextOptions.MarginMeasureTypeEnum.Pixels,
    Font = new SignatureFont
    {
        FontFamily = "Arial",
        FontSize = 12,
        Bold = true,
        Italic = false,
        Underline = false
    },
    ForeColor = new Color {Web = "BlueViolet"},
    Border = new BorderLine
    {
        Color = new Color {Web = "DarkOrange"},
        Visible = true,
        Style = BorderLine.StyleEnum.Dash
    },
    BackgroundColor = new Color {Web = "DarkOrange"},
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
    SaveOptions = new SaveOptions { OutputFilePath = "signedText_one-page.docx", SaveFormat = "docx" },
    Options = new List<SignOptions> { options }
};
// Create request.
var request = new CreateSignaturesRequest(signSettings);
// Call api method with request.
var response = apiInstance.CreateSignatures(request);

```

Java

```java

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-java-samples
String MyAppKey = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
String MyAppSid = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud

Configuration configuration = new Configuration(MyAppSid, MyAppKey);
SignApi apiInstance = new SignApi(configuration);

FFileInfo fileInfo = new FileInfo();
fileInfo.setFilePath("Signaturedocs\\one-page.docx");
fileInfo.setPassword(null);
fileInfo.setVersionId(null);
fileInfo.setStorageName(Constants.MYStorage);

InfoSettings infoSettings = new InfoSettings();
infoSettings.setFileInfo(fileInfo);

SignTextOptions options = new SignTextOptions();
options.setSignatureType(SignatureTypeEnum.TEXT);

// set signature properties
options.setText("John Smith");

// set signature position on a page
options.setLeft(100);
options.setTop(100);
options.setWidth(100);
options.setHeight(100);
options.setLocationMeasureType(LocationMeasureTypeEnum.PIXELS);
options.setSizeMeasureType(SizeMeasureTypeEnum.PIXELS);
options.setStretch(StretchEnum.NONE);
options.setRotationAngle(0);
options.setHorizontalAlignment(HorizontalAlignmentEnum.NONE);
options.setVerticalAlignment(VerticalAlignmentEnum.NONE);

Padding padding = new Padding();
padding.setAll(5);
options.setMargin(padding);
options.setMarginMeasureType(MarginMeasureTypeEnum.PIXELS);

Color backgroundColor = new Color();
backgroundColor.setWeb("DarkOrange");
options.setBackgroundColor(backgroundColor);

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
saveOptions.setOutputFilePath("Signaturedocs\\signedText_one-page.docx");

SignSettings signSettings = new SignSettings();
signSettings.setFileInfo(fileInfo);
signSettings.addOptionsItem(options);
signSettings.setSaveOptions(saveOptions);

CreateSignaturesRequest request = new CreateSignaturesRequest(signSettings);

SignResult response = apiInstance.createSignatures(request);

```

PHP

```php

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-php-samples
use GroupDocs\Signature\Model;
use GroupDocs\Signature\Model\Requests;

$AppSid = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
$AppKey = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud

$configuration = new GroupDocs\Signature\Configuration();
$configuration->setAppSid($AppSid);
$configuration->setAppKey($AppKey);

$apiInstance = new GroupDocs\Signature\SignApi($configuration);

$fileInfo = new GroupDocs\Signature\Model\FileInfo();
$fileInfo->setFilePath("signaturedocs\one-page.docx");
$fileInfo->setPassword("");

$settings = new GroupDocs\Signature\Model\SignSettings();
$settings->setFileInfo($fileInfo);

$saveOptions = new GroupDocs\Signature\Model\SaveOptions();
$saveOptions->setOutputFilePath("signaturedocs\signedTextOne_page.docx");
$settings->setSaveOptions($saveOptions);

$options = new GroupDocs\Signature\Model\SignTextOptions();
$options->setPage(1);
$options->setAllPages(false);
$options->setSignatureType(GroupDocs\Signature\Model\OptionsBase::SIGNATURE_TYPE_TEXT);
$options->setText("GroupDocs Cloud");
$options->setLeft(100);
$options->setTop(100);
$options->setWidth(100);
$options->setHeight(100);
$options->setLocationMeasureType(GroupDocs\Signature\Model\SignTextOptions::LOCATION_MEASURE_TYPE_PIXELS);
$options->setSizeMeasureType(GroupDocs\Signature\Model\SignTextOptions::SIZE_MEASURE_TYPE_PIXELS);
$options->setStretch(GroupDocs\Signature\Model\SignTextOptions::STRETCH_NONE);
$options->setRotationAngle(0);
$options->setHorizontalAlignment(GroupDocs\Signature\Model\SignTextOptions::HORIZONTAL_ALIGNMENT_NONE);
$options->setVerticalAlignment(GroupDocs\Signature\Model\SignTextOptions::VERTICAL_ALIGNMENT_NONE);

$padding = new GroupDocs\Signature\Model\Padding();
$padding->setAll(5);
$options->setMargin($padding);
$options->setMarginMeasureType(GroupDocs\Signature\Model\SignTextOptions::MARGIN_MEASURE_TYPE_PIXELS);
$color = new GroupDocs\Signature\Model\Color();
$color->setWeb("BlueViolet");
$options->setForeColor($color);

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

Node

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-node-samples
global.signature_cloud = require("groupdocs-signature-cloud");

global.appSid = "XXXX-XXXX-XXXX-XXXX"; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
global.appKey = "XXXXXXXXXXXXXXXX"; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud

global.signApi = signature_cloud.SignApi.fromKeys(appSid, appKey);

let fileInfo = new signature_cloud.FileInfo();
fileInfo.filePath = "signaturedocs/one-page.docx";

let opts = new signature_cloud.SignTextOptions();
opts.signatureType = signature_cloud.OptionsBase.SignatureTypeEnum.Text;
opts.text = 'GroupDocs.Signature Cloud';

// set signature position on a page
opts.left = 100;
opts.top = 100;
opts.width = 100;
opts.height = 100;
opts.locationMeasureType = signature_cloud.SignTextOptions.LocationMeasureTypeEnum.Pixels;
opts.sizeMeasureType = signature_cloud.SignTextOptions.SizeMeasureTypeEnum.Pixels;
opts.stretch = signature_cloud.SignTextOptions.StretchEnum.None;
opts.rotationAngle = 0;
opts.horizontalAlignment = signature_cloud.SignTextOptions.HorizontalAlignmentEnum.None;
opts.verticalAlignment = signature_cloud.SignTextOptions.VerticalAlignmentEnum.None;

opts.margin = new signature_cloud.Padding();
opts.margin.all = 5;
opts.marginMeasureType = signature_cloud.SignTextOptions.MarginMeasureTypeEnum.Pixels;

// set signature appearance
opts.font = new signature_cloud.SignatureFont();
opts.font.fontFamily = "Arial";
opts.font.fontSize = 12;
opts.font.bold = true;
opts.font.italic = false;
opts.font.underline = false;

opts.foreColor = new signature_cloud.Color();
opts.foreColor.web = "BlueViolet";

opts.backgroundColor = new signature_cloud.Color();
opts.backgroundColor.web = "DarkOrange";

opts.page = 1;

let settings = new signature_cloud.SignSettings();
settings.fileInfo = fileInfo;
settings.options = [opts];

settings.saveOptions = new signature_cloud.SaveOptions();
settings.saveOptions.outputFilePath = "signaturedocs/signedText_one-page.docx";

let request = new signature_cloud.CreateSignaturesRequest(settings);
let response = await signApi.createSignatures(request);

```

Python

```python

# For complete examples and data files, please go to https://github.com/groupdocs-signature_cloud-cloud/groupdocs-signature_cloud-cloud-python-samples
from groupdocs_signature_cloud import *
import groupdocs_signature_cloud

app_sid = "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
app_key = "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud

api = groupdocs_signature_cloud.SignApi.from_keys(app_sid, app_key)

fileInfo = FileInfo()
fileInfo.file_path = "signaturedocs\\one-page.docx"

opts = SignTextOptions()
opts.signature_type = 'Text'
opts.text = 'GroupDocs.Signature Cloud'

# set signature position on a page
opts.left = 100
opts.top = 100
opts.width = 100
opts.height = 100
opts.location_measure_type = "Pixels"
opts.size_measure_type = "Pixels"
opts.stretch = "None"
opts.rotation_angle = 0
opts.horizontal_alignment = "None"
opts.vertical_alignment = "None"
opts.margin = Padding()
opts.margin.all = 5
opts.margin_measure_type = "Pixels"

# set signature appearance
opts.font = SignatureFont()
opts.font.font_family = "Arial"
opts.font.font_size = 12
opts.font.bold = True
opts.font.italic = False
opts.font.underline = False
opts.fore_color = Color()
opts.fore_color.web = "BlueViolet"
opts.background_color = Color()
opts.background_color.web = "DarkOrange"

opts.page = 1

settings = SignSettings()
settings.options = [opts]
settings.save_options = SaveOptions()
settings.save_options.output_file_path = "signaturedocs\\signedTextOne_page.docx"
settings.file_info = fileInfo

request = CreateSignaturesRequest(settings)
response = api.create_signatures(request)

```

Ruby

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-ruby-samples
require 'groupdocs_signature_cloud'

$app_sid = "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
$app_key = "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud

api = GroupDocsSignatureCloud::SignApi.from_keys($app_sid, $app_key)

$info = GroupDocsSignatureCloud::FileInfo.new()
$info.file_path = "signaturedocs\\one-page.docx"

$opts = GroupDocsSignatureCloud::SignTextOptions.new()
$opts.signature_type = "Text"
$opts.text = 'GroupDocs.Signature Cloud'

# set signature position on a page
$opts.left = 100
$opts.top = 100
$opts.width = 100
$opts.height = 100
$opts.location_measure_type = "Pixels"
$opts.size_measure_type = "Pixels"
$opts.stretch = "None"
$opts.rotation_angle = 0
$opts.horizontal_alignment = "None"
$opts.vertical_alignment = "None"

$opts.margin = GroupDocsSignatureCloud::Padding.new()
$opts.margin.all = 5
$opts.margin_measure_type = "Pixels"

# set signature appearance
$opts.font = GroupDocsSignatureCloud::SignatureFont.new()
$opts.font.font_family = "Arial"
$opts.font.font_size = 12
$opts.font.bold = true
$opts.font.italic = false
$opts.font.underline = false

$opts.fore_color = GroupDocsSignatureCloud::Color.new()
$opts.fore_color.web = "BlueViolet"

$opts.background_color = GroupDocsSignatureCloud::Color.new()
$opts.background_color.web = "DarkOrange"

$opts.page = 1

$settings = GroupDocsSignatureCloud::SignSettings.new()
$settings.options = [$opts]

$settings.save_options = GroupDocsSignatureCloud::SaveOptions.new()
$settings.save_options.output_file_path = "signaturedocs\\signedTextOne_page.docx"
$settings.file_info = $info

$request = GroupDocsSignatureCloud::CreateSignaturesRequest.new($settings)

# Executing an API.
$response = api.create_signatures($request)

```

