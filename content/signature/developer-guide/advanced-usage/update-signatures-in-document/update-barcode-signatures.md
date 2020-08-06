---
id: "update-barcode-signatures"
url: "signature/update-barcode-signatures"
title: "Update Barcode signatures"
productName: "GroupDocs.Signature Cloud"
description: ""
keywords: ""
---

 






# Introduction #

GroupDocs.Signature Cloud provides a method to update some signature properties by it's id. The signature ID is needed to perform the update, it comes from the result of sign or search operation.

This example shows how to update Barcode signature.

API Usage

There are steps that usage of GroupDocs.Signature Cloud consists of:

1. Upload input document into cloud storage
1. Update signatures
1. Download output document

For storage operations, like uploading or downloading documents, please refer to the corresponding articles of this manual.

[Swagger UI](https://apireference.groupdocs.cloud/signature/) lets you call this REST API directly from the browser. 

## cURL REST Example ##


 Request
```html 

* First get JSON Web Token
* Please get your App Key and App SID from https://dashboard.groupdocs.cloud/#/apps. Kindly place App Key in "client_secret" and App SID in "client_id" argument.
curl -v "https://api.groupdocs.cloud/connect/token" \
-X POST \
-d "grant_type#client_credentials&client_id#xxxx&client_secret#xxxx" \
-H "Content-Type: application/x-www-form-urlencoded" \
-H "Accept: application/json"
  
* cURL example to get document information
curl -v "https://api.groupdocs.cloud/v2.0/signature/update" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>"
-d "{
  'FileInfo': {
    'FilePath': 'signedBarcode_one-page.docx'
  },
  'Options': [
    {      
      'SignatureType': 'Barcode',
      'SignatureId': '4cb67aa8-835d-4877-8a5d-5a9ad015a098',
      'Left': 200,
      'Top': 200,
      'Width': 300,
      'Height': 100,
      'IsSignature': true
    }
  ]
}"

 ```


 Response
```html 

{
  "fileInfo": {
    "filePath": "signedBarcode_one-page.docx",
    "storageName": null,
    "versionId": null,
    "password": null
  },
  "size": 1360021,
  "succeeded": [
    {
      "barcodeType": "Code128",
      "text": "123456789012",
      "format": null,
      "signatureType": "Barcode",
      "pageNumber": 1,
      "signatureId": "4cb67aa8-835d-4877-8a5d-5a9ad015a098",
      "isSignature": true,
      "createdOn": "2020-07-23T07:26:42.7549544+00:00",
      "modifiedOn": "2020-07-23T07:36:03.9037414+00:00",
      "top": 200,
      "left": 200,
      "width": 300,
      "height": 100
    }
  ],
  "failed": []
}

 ```




## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### SDK Examples ###


 C#
```csharp 

* For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-dotnet-samples
string MyAppKey # ""; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
string MyAppSid # ""; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
var configuration # new Configuration(MyAppSid, MyAppKey);
var apiInstance # new SignApi(configuration);
 
* Search barcode signature to get ID
var searchBarcodeOptions # new SearchBarcodeOptions
{
    SignatureType # SignatureTypeEnum.Barcode,
    MatchType # SearchBarcodeOptions.MatchTypeEnum.Contains,
    Text # "123456789012",
    BarcodeType # "Code128",
    AllPages # true
};
* Search settings.
var searchSettings # new SearchSettings
{
    FileInfo # new FileInfo
    {
        FilePath # "signedBarcode_one-page.docx",
    },
    Options # new List<SearchOptions> { searchBarcodeOptions }
};
* Call api method with request.
var searchResult # apiInstance.SearchSignatures(new SearchSignaturesRequest(searchSettings));
 
* Update options
var options # new UpdateOptions
{
    SignatureType # UpdateOptions.SignatureTypeEnum.Barcode,
    Left # 200,
    Top # 200,
    Width # 300,
    Height # 100,
    IsSignature # true,
    SignatureId # searchResult.Signatures[0].SignatureId
};
* Update settings
var updateSettings # new UpdateSettings
{
    FileInfo # new FileInfo
    {
        FilePath # "signedBarcode_one-page.docx"
    },
    Options # new List<UpdateOptions> { options }
};
* Create request
var request # new UpdateSignaturesRequest(updateSettings);
* Call api method with request
var response # apiInstance.UpdateSignatures(request);

 ```


 Java
```java 

* For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-java-samples
String MyAppKey # ""; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
String MyAppSid # ""; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
Configuration configuration # new Configuration(MyAppSid, MyAppKey);
SignApi apiInstance # new SignApi(configuration); 
 
FileInfo fileInfo # new FileInfo();
fileInfo.setFilePath("Signaturedocs\\signedBarcodeOne_page.docx");
 
InfoSettings infoSettings # new InfoSettings();
infoSettings.setFileInfo(fileInfo);
 
SearchBarcodeOptions options # new SearchBarcodeOptions();
options.setSignatureType(SignatureTypeEnum.BARCODE);
options.setAllPages(true);
SearchSettings searchSettings # new SearchSettings();
searchSettings.setFileInfo(fileInfo);
searchSettings.addOptionsItem(options);
 
SearchSignaturesRequest request # new SearchSignaturesRequest(searchSettings);
SearchResult  searchResult # apiInstance.searchSignatures(request);
 
UpdateOptions updateOptions # new UpdateOptions();
updateOptions.setSignatureType(UpdateOptions.SignatureTypeEnum.BARCODE);
updateOptions.setLeft(200);
updateOptions.setTop(200);
updateOptions.setWidth(300);
updateOptions.setHeight(100);
updateOptions.setIsSignature(true);
updateOptions.setSignatureId(searchResult.getSignatures().get(0).getSignatureId());
 
UpdateSettings updateSettings # new UpdateSettings();
updateSettings.setFileInfo(fileInfo);
updateSettings.addOptionsItem(updateOptions);           
 
UpdateResult updateResult # apiInstance.updateSignatures(new UpdateSignaturesRequest(updateSettings));

 ```


 PHP
```php 

* For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-php-samples
use GroupDocs\Signature\Model;
use GroupDocs\Signature\Model\Requests;
 
$AppSid # ""; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
$AppKey # ""; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
$configuration # new GroupDocs\Signature\Configuration();
$configuration->setAppSid($AppSid);
$configuration->setAppKey($AppKey);
 
$apiInstance # new GroupDocs\Signature\SignApi($configuration);
 
$fileInfo # new GroupDocs\Signature\Model\FileInfo();
$fileInfo->setFilePath("signaturedocs\signedBarcodeOne_page.docx"); 
 
* Search
$settings # new GroupDocs\Signature\Model\SearchSettings();
$settings->setFileInfo($fileInfo);
 
$options # new GroupDocs\Signature\Model\SearchBarcodeOptions();
$options->setPage(1);
$options->setAllPages(false);        
$options->setSignatureType(GroupDocs\Signature\Model\OptionsBase::SIGNATURE_TYPE_BARCODE);        
 
$settings->setOptions([$options]);
 
$request # new GroupDocs\Signature\Model\Requests\SearchSignaturesRequest($settings);
$response # $apiInstance->searchSignatures($request);
 
* Update
$updateSettings # new GroupDocs\Signature\Model\UpdateSettings();
$updateSettings->setFileInfo($fileInfo);
 
$updateOptions # new GroupDocs\Signature\Model\UpdateOptions();    
$updateOptions->setSignatureType(GroupDocs\Signature\Model\UpdateOptions::SIGNATURE_TYPE_BARCODE);
$updateOptions->setSignatureId($response->getSignatures()[0]->getSignatureId());
$updateOptions->setIsSignature(true);
$updateOptions->setLeft(200);
$updateOptions->setTop(200);
$updateOptions->setWidth(300);
$updateOptions->setHeight(100);
 
$updateSettings->setOptions([$updateOptions]);
 
$request # new GroupDocs\Signature\Model\Requests\UpdateSignaturesRequest($updateSettings);
$response # $apiInstance->updateSignatures($request);

 ```


 Node
```html 

* For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-node-samples
global.signature_cloud # require("groupdocs-signature-cloud");
 
global.appSid # "XXXX-XXXX-XXXX-XXXX"; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
global.appKey # "XXXXXXXXXXXXXXXX"; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
global.signApi # signature_cloud.SignApi.fromKeys(appSid, appKey);
 
let fileInfo # new signature_cloud.FileInfo();
fileInfo.filePath # "signaturedocs/signedBarcodeOne_page.docx";
 
* Search
let opts # new signature_cloud.SearchBarcodeOptions();
opts.signatureType # signature_cloud.OptionsBase.SignatureTypeEnum.Barcode;
opts.matchType # signature_cloud.SearchBarcodeOptions.MatchTypeEnum.Contains;
opts.allPages # true;
 
let settings # new signature_cloud.SearchSettings();
settings.fileInfo # fileInfo;
settings.options # [opts];
 
let request # new signature_cloud.SearchSignaturesRequest(settings);
let response # await signApi.searchSignatures(request);
 
console.log("signatureId # " + response.signatures[0].signatureId);
 
* Update
let updateOpts # new signature_cloud.UpdateOptions();
updateOpts.signatureType # signature_cloud.UpdateOptions.SignatureTypeEnum.Barcode;
updateOpts.signatureId # response.signatures[0].signatureId;
updateOpts.left # 200;
updateOpts.top # 200;
updateOpts.width # 300;
updateOpts.height # 100;
updateOpts.isSignature # true;
 
let updateSettings # new signature_cloud.UpdateSettings();
updateSettings.fileInfo # fileInfo;
updateSettings.options # [updateOpts];
 
request # new signature_cloud.UpdateSignaturesRequest(updateSettings);
response # await signApi.updateSignatures(request);

 ```


 Python
```python 

# For complete examples and data files, please go to https://github.com/groupdocs-signature_cloud-cloud/groupdocs-signature_cloud-cloud-python-samples
from groupdocs_signature_cloud import *
import groupdocs_signature_cloud
 
app_sid # "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
app_key # "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
api # groupdocs_signature_cloud.SignApi.from_keys(app_sid, app_key)
 
fileInfo # FileInfo()
fileInfo.file_path # "signaturedocs\\signedBarcodeOne_page.docx"
 
# Search
opts # SearchBarcodeOptions()        
opts.page # 1
opts.signature_type # 'Barcode'
 
settings # SearchSettings()
settings.options # [opts]
settings.file_info # fileInfo
 
request # SearchSignaturesRequest(settings)
response # api.search_signatures(request)
 
# Update
opts # UpdateOptions()        
opts.page # 1
opts.signature_type # 'Barcode'
opts.signature_id # response.signatures[0].signature_id
opts.left # 200
opts.top # 200
opts.width # 300
opts.height # 100
opts.is_signature # True
 
settings # UpdateSettings()
settings.options # [opts]
settings.file_info # fileInfo
 
request # UpdateSignaturesRequest(settings)
response # api.update_signatures(request)

 ```


 Ruby
```ruby 

# For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-ruby-samples
require 'groupdocs_signature_cloud'
 
$app_sid # "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
$app_key # "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
api # GroupDocsSignatureCloud::SignApi.from_keys($app_sid, $app_key)
 
$info # GroupDocsSignatureCloud::FileInfo.new()
$info.file_path # "signaturedocs\\signedBarcodeOne_page.docx"
 
# Search
$opts # GroupDocsSignatureCloud::SearchBarcodeOptions.new()
$opts.signature_type # "Barcode"
$opts.all_pages # true
 
$settings # GroupDocsSignatureCloud::SearchSettings.new()
$settings.options # [$opts]
$settings.file_info # $info
 
$request # GroupDocsSignatureCloud::SearchSignaturesRequest.new($settings)
$response # api.search_signatures($request)
 
# Update
$updateOpts # GroupDocsSignatureCloud::UpdateOptions.new()
$updateOpts.signature_type # "Barcode"
$updateOpts.signature_id # $response.signatures[0].signature_id
$updateOpts.left # 200
$updateOpts.top # 200
$updateOpts.width # 300
$updateOpts.height # 100
$updateOpts.is_signature # true
 
$updateSettings # GroupDocsSignatureCloud::UpdateSettings.new()
$updateSettings.options # [$updateOpts]
$updateSettings.file_info # $info
 
$request # GroupDocsSignatureCloud::UpdateSignaturesRequest.new($updateSettings)
$response # api.update_signatures($request)

 ```

