---
id: "quick-start"
url: "signature/quick-start"
title: "Quick Start"
productName: "GroupDocs.Signature Cloud"
weight: 3
description: ""
keywords: ""
toc: True
---

## Create an account

Creating an account is very simple. Go to [https://dashboard.groupdocs.cloud](https://dashboard.groupdocs.cloud/#/) to create a free account.

## Create an API client app

Before you can make any requests to GroupDocs Cloud API you need to get a **Client Id** and a **Client Secret**.
This will will be used to invoke GroupDocs Cloud API. You can get it by creating a new [Application](https://dashboard.groupdocs.cloud/applications).

## Install the SDK of your choice

GroupDocs for Cloud SDK is written in different languages, all you need to get started is adding our [SDK]({{< ref "signature/getting-started/available-sdks.md" >}}) to your existing project.

## Make an API request from the SDK of your choice

Use the **Client Id** and **Client Secret** from the API app client you created in step one and replace in the corresponding code.
Below is an example demonstrating how to sign pdf document with digital signature using GroupDocs.Signature Cloud.

{{< alert style="info" >}}The GitHub repository for [GroupDocs.Signature Cloud](https://github.com/groupdocs-signature-cloud) has a complete set of examples, demonstrating our API capabilities.{{< /alert >}}

## SDK example

{{< tabs "example2">}} {{< tab "C#" >}}

```csharp

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-dotnet-samples
string MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
string MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

var configuration = new Configuration(MyClientId, MyClientSecret);
var apiInstance = new SignApi(configuration);
// Sign options
var options = new SignDigitalOptions
{
    SignatureType = SignatureTypeEnum.Digital,
    ImageFilePath = "signature.jpg",
    CertificateFilePath = "temp.pfx",
    Password = "1234567890",
    Left = 100,
    Top = 100,
    Width = 200,
    Height = 200,
    LocationMeasureType = SignImageOptions.LocationMeasureTypeEnum.Pixels,
    SizeMeasureType = SignImageOptions.SizeMeasureTypeEnum.Pixels,
    RotationAngle = 0,
    HorizontalAlignment = SignImageOptions.HorizontalAlignmentEnum.None,
    VerticalAlignment = SignImageOptions.VerticalAlignmentEnum.None,
    Margin = new Padding {All = 5},
    MarginMeasureType = SignImageOptions.MarginMeasureTypeEnum.Pixels,
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
    FileInfo = new Sdk.Model.FileInfo
    {
        FilePath = "sample2.pdf"
    },
    SaveOptions = new SaveOptions { OutputFilePath = "signedDigital_sample2.pdf", SaveFormat = "pdf" },
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
fileInfo.setFilePath("Signaturedocs\\sample2.pdf");
fileInfo.setPassword(null);
fileInfo.setVersionId(null);
fileInfo.setStorageName(Constants.MYStorage);

InfoSettings infoSettings = new InfoSettings();
infoSettings.setFileInfo(fileInfo);

SignDigitalOptions options = new SignDigitalOptions();
options.setSignatureType(SignatureTypeEnum.DIGITAL);

// set signature properties
options.setImageFilePath("Signaturedocs\\signature.jpg");
options.setCertificateFilePath("Signaturedocs\\temp.pfx");
options.setPassword("1234567890");

// set signature position on a page
options.setLeft(100);
options.setTop(100);
options.setWidth(200);
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
saveOptions.setOutputFilePath("Signaturedocs\\signedDigital_sample2.pdf");

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
$saveOptions->setOutputFilePath("signaturedocs\signedDigitalOne_page.docx");
$settings->setSaveOptions($saveOptions);

$options = new GroupDocs\Signature\Model\SignDigitalOptions();
$options->setPage(1);
$options->setAllPages(false);
$options->setSignatureType(GroupDocs\Signature\Model\OptionsBase::SIGNATURE_TYPE_DIGITAL);
$options->setImageFilePath("signaturedocs\\signature.jpg");
$options->setCertificateFilePath("signaturedocs\\temp.pfx");
$options->setPassword("1234567890");
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
fileInfo.filePath = "signaturedocs/sample2.pdf";

let opts = new signature_cloud.SignDigitalOptions();
opts.signatureType = signature_cloud.OptionsBase.SignatureTypeEnum.Digital;
opts.imageFilePath = "signaturedocs/signature.jpg";
opts.certificateFilePath = "signaturedocs/temp.pfx";
opts.password = "1234567890";

let settings = new signature_cloud.SignSettings();
settings.fileInfo = fileInfo;
settings.options = [opts];

settings.saveOptions = new signature_cloud.SaveOptions();
settings.saveOptions.outputFilePath = "signaturedocs/signedDigital_sample2.pdf";

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

opts = SignDigitalOptions()
opts.signature_type = 'Digital'
opts.image_file_path = "signaturedocs\\signature.jpg"
opts.certificate_file_path = "signaturedocs\\temp.pfx"
opts.password = '1234567890'

# set signature position on a page
opts.left = 100
opts.top = 100
opts.width = 200
opts.height = 100
opts.location_measure_type = "Pixels"
opts.size_measure_type = "Pixels"
opts.rotation_angle = 0
opts.horizontal_alignment = "None"
opts.vertical_alignment = "None"
opts.margin = Padding()
opts.margin.all = 5
opts.margin_measure_type = "Pixels"

opts.page = 1

settings = SignSettings()
settings.options = [opts]
settings.save_options = SaveOptions()
settings.save_options.output_file_path = "signaturedocs\\signedDigitalOne_page.docx"
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

$opts = GroupDocsSignatureCloud::SignDigitalOptions.new()
$opts.signature_type = 'Digital'
$opts.image_file_path = "signaturedocs\\signature.jpg"
$opts.certificate_file_path = "signaturedocs\\temp.pfx"
$opts.password = '1234567890'

$settings = GroupDocsSignatureCloud::SignSettings.new()
$settings.options = [$opts]

$settings.save_options = GroupDocsSignatureCloud::SaveOptions.new()
$settings.save_options.output_file_path = "signaturedocs\\signedDigitalOne_page.docx"
$settings.file_info = $info

$request = GroupDocsSignatureCloud::CreateSignaturesRequest.new($settings)

# Executing an API.
$response = api.create_signatures($request)

```

{{< /tab >}} {{< /tabs >}}
