---
id: "sign-document-with-barcode-signature"
url: "signature/sign-document-with-barcode-signature"
title: "Sign document with Barcode signature"
productName: "GroupDocs.Signature Cloud"
description: ""
keywords: ""
toc: True
---

A **barcode** or **bar code** is a way of presenting data in a visual, machine-readable form. Generally speaking, barcode is an image of rectangular form that consists of parallel black lines and white spaces of different widths.
Barcodes are used in various areas where quick identification is necessary - as part of the purchase process in retail stores, in warehouses to track inventory, and on invoices to assist in accounting, among many other uses.

![barcode](/signature/images/GS1-DataBar_Expanded_01.gif)

Barcodes allow to store product related data like manufacturing and expiry dates, manufacturer name, country of the origin and product price. There are plenty of barcode types nowadays because different companies use different amount of number and bar combinations in their barcodes dependent on their needs. From document signature perspective Barcode may contain different characters (letters, digits or symbols) and have a various length and its size depending on the type and settings to keep signature information, title, subject or short encrypted data.

GroupDocs.Signature Cloud supports wide range or Barcode types that can be used to create electronic signature within the documents. Please refer to [Getting supported Barcode Types](/signature/get-supported-barcodes) article to get the full list of supported barcodes.
To specify different options for Barcode signature GroupDocs.Signature Cloud provides SignBarcodeOptions class. The main fields are:

* BarcodeType - specifies Barcode type (AustralianPost, Codabar, EAN13, OPC, etc.);
* Text - specifies Barcode text.

## API usage

There are steps that usage of GroupDocs.Signature Cloud consists of:

1. Upload input document into cloud storage and other files, like digital certificate or image stamp
1. Sign document
1. Download output document

For storage operations, like uploading or downloading documents, please refer to the corresponding articles of this manual.

[Swagger UI](https://apireference.groupdocs.cloud/signature/) lets you call this REST API directly from the browser.

## cURL example

{{< tabs "example1">}} {{< tab "Request" >}}

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
      'AllPages': true,
      'SignatureType': 'Barcode',
      'BarcodeType': 'Code128',
      'Text': '123456789012',
      'Left': 100,
      'Top': 100,
      'Width': 300,
      'Height': 100
    }
  ],
  'SaveOptions': {
    'OutputFilePath': 'signaturedocs/signedBarcode_one-page.docx'
  }
}"

```

{{< /tab >}} {{< tab "Response" >}}

```javascript
{
  "fileInfo": {
    "filePath": "signaturedocs/signedBarcode_one-page.docx",
    "storageName": null,
    "versionId": null,
    "password": null
  },
  "size": 1360009,
  "downloadUrl": "https://api-qa.groupdocs.cloud/v2.0/signature/storage/file/signaturedocs/signedBarcode_one-page.docx",
  "succeeded": [
    {
      "barcodeType": "Code128",
      "text": "123456789012",
      "format": "Portable Network Graphic",
      "signatureType": "Barcode",
      "pageNumber": 1,
      "signatureId": "563fbe1b-41a9-416e-8f3a-32c0abfce70b",
      "isSignature": true,
      "createdOn": "2020-07-21T08:05:17.022145+00:00",
      "modifiedOn": "2020-07-21T08:05:17.022145+00:00",
      "top": 100,
      "left": 100,
      "width": 300,
      "height": 100
    }
  ],
  "failed": []
}

```

{{< /tab >}} {{< /tabs >}}

## SDK examples

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](/signature/available-sdks).



{{< tabs "example2">}} {{< tab "C#" >}}

```csharp

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-dotnet-samples
string MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
string MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

var configuration = new Configuration(MyClientId, MyClientSecret);
var apiInstance = new SignApi(configuration);
// Sign options.
var options = new SignBarcodeOptions
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
    SaveOptions = new SaveOptions { OutputFilePath = "signedBarcode_one-page.docx", SaveFormat = "docx" },
    Options = new List<SignOptions> { options }
};
// Create request.
var request = new CreateSignaturesRequest(signSettings);
// Call api method with request.
var response = apiInstance.CreateSignatures(request);

```

{{< /tab >}} {{< tab "Java" >}}

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

SignBarcodeOptions options = new SignBarcodeOptions();
options.setSignatureType(SignatureTypeEnum.BARCODE);

// set signature properties
options.setText("123456789012");
options.setBarcodeType("Code128");
options.setCodeTextAlignment(CodeTextAlignmentEnum.NONE);

// set signature position on a page
options.setLeft(100);
options.setTop(100);
options.setWidth(300);
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

Padding innerMargins = new Padding();
innerMargins.setAll(2);
options.setInnerMargins(innerMargins);

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
saveOptions.setOutputFilePath("Signaturedocs\\signedBarcodeOne_page.docx");

SignSettings signSettings = new SignSettings();
signSettings.setFileInfo(fileInfo);
signSettings.addOptionsItem(options);
signSettings.setSaveOptions(saveOptions);

CreateSignaturesRequest request = new CreateSignaturesRequest(signSettings);

SignResult response = apiInstance.createSignatures(request);

```

{{< /tab >}} {{< tab "PHP" >}}

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
$saveOptions->setOutputFilePath("signaturedocs\signedBarcodeOne_page.docx");
$settings->setSaveOptions($saveOptions);

$options = new GroupDocs\Signature\Model\SignBarcodeOptions();
$options->setPage(1);
$options->setAllPages(false);
$options->setSignatureType(GroupDocs\Signature\Model\OptionsBase::SIGNATURE_TYPE_BARCODE);
$options->setBarcodeType("Code128");
$options->setText("123456789012");
$options->setCodeTextAlignment(GroupDocs\Signature\Model\SignBarcodeOptions::CODE_TEXT_ALIGNMENT_NONE);
$options->setLeft(100);
$options->setTop(100);
$options->setWidth(300);
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
$padding = new GroupDocs\Signature\Model\Padding();
$padding->setAll(2);
$options->setInnerMargins($padding);

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

{{< /tab >}} {{< tab "Node.js" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-node-samples
global.signature_cloud = require("groupdocs-signature-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

global.signApi = signature_cloud.SignApi.fromKeys(clientId, clientSecret);

let fileInfo = new signature_cloud.FileInfo();
fileInfo.filePath = "signaturedocs/one-page.docx";

let opts = new signature_cloud.SignBarcodeOptions();
opts.signatureType = signature_cloud.OptionsBase.SignatureTypeEnum.Barcode;
opts.barcodeType = 'Code39Standard';
opts.text = '123456789012';
opts.codeTextAlignment = signature_cloud.SignBarcodeOptions.CodeTextAlignmentEnum.None;

// set signature position on a page
opts.left = 100;
opts.top = 100;
opts.width = 300;
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

opts.innerMargins = new signature_cloud.Padding();
opts.innerMargins.all = 2;

opts.page = 1;
opts.allPages = false;

let settings = new signature_cloud.SignSettings();
settings.fileInfo = fileInfo;
settings.options = [opts];
settings.saveOptions = new signature_cloud.SaveOptions();
settings.saveOptions.outputFilePath = "signaturedocs/signedBarcodeOne_page.docx";

let request = new signature_cloud.CreateSignaturesRequest(settings);
let response = await signApi.createSignatures(request);

```

{{< /tab >}} {{< tab "Python" >}}

```python

# For complete examples and data files, please go to https://github.com/groupdocs-signature_cloud-cloud/groupdocs-signature_cloud-cloud-python-samples
from groupdocs_signature_cloud import *
import groupdocs_signature_cloud

client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

api = groupdocs_signature_cloud.SignApi.from_keys(client_id, client_secret)

fileInfo = FileInfo()
fileInfo.file_path = "signaturedocs\\one-page.docx"

opts = SignBarcodeOptions()
opts.signature_type = 'Barcode'
opts.text = '123456789012'
opts.barcode_type = 'Code128'
opts.code_text_alignment = 'None'

# set signature position on a page
opts.left = 100
opts.top = 100
opts.width = 300
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

opts.inner_margins = Padding()
opts.inner_margins.all = 2

opts.page = 1

settings = SignSettings()
settings.options = [opts]
settings.save_options = SaveOptions()
settings.save_options.output_file_path = "signaturedocs\\signedBarcodeOne_page.docx"
settings.file_info = fileInfo

request = CreateSignaturesRequest(settings)
response = api.create_signatures(request)

```

{{< /tab >}} {{< tab "Ruby" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-ruby-samples
require 'groupdocs_signature_cloud'

$client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

api = GroupDocsSignatureCloud::SignApi.from_keys($client_id, $client_secret)

$info = GroupDocsSignatureCloud::FileInfo.new()
$info.file_path = "signaturedocs\\one-page.docx"

$opts = GroupDocsSignatureCloud::SignBarcodeOptions.new()
$opts.signature_type = 'Barcode'
$opts.barcode_type = 'Code128'
$opts.text = '123456789012'
$opts.code_text_alignment = 'None'

# set signature position on a page
$opts.left = 100
$opts.top = 100
$opts.width = 300
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

$opts.inner_margins = GroupDocsSignatureCloud::Padding.new()
$opts.inner_margins.all = 2

$opts.page = 1

$settings = GroupDocsSignatureCloud::SignSettings.new()
$settings.options = [$opts]

$settings.save_options = GroupDocsSignatureCloud::SaveOptions.new()
$settings.save_options.output_file_path = "signaturedocs\\signedBarcodeOne_page.docx"

$settings.file_info = $info
$request = GroupDocsSignatureCloud::CreateSignaturesRequest.new($settings)

# Executing an API.
$response = api.create_signatures($request)

```

{{< /tab >}} {{< /tabs >}}
