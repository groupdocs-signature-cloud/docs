---
id: "working-with-folder-api"
url: "signature/working-with-folder-api"
title: "Working with Folder API"
productName: "GroupDocs.Signature Cloud"
weight: 12
description: ""
keywords: ""
---






# Get the File Listing of a Specific Folder #

This API allows you to get a list of all files of a specific folder from the specified Cloud Storage. If you do not pass storage name API will find folder in GroupDocs Cloud Storage. 

## API Explorer ##

[GroupDocs.signature Cloud API Reference](https://apireference.groupdocs.cloud/signature/) lets you to try out [List Files in a Folder API](https://apireference.groupdocs.cloud/signature/#/Folder/GetFilesList) right away in your browser. It allows you to effortlessly interact and try out every single operation that our APIs exposes.
|---|---|---|---

#### Request parameters ####

|Parameter|Description
|---|---
|**path**|Path of the file including file name and extension e.g. /Folder1/file.ext

Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used


## cURL Example ##





 Request

```html 
curl -X GET "https://api.groupdocs.cloud/v2.0/signature/storage/folder/signaturedocs?storageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"

 ```




 Response

```html 
{
  "value": [
    {
      "name": "four-pages.docx",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:35:38+00:00",
      "size": 8651,
      "path": "/signaturedocs/four-pages.docx"
    },
    {
      "name": "one-page.docx",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:17:34+00:00",
      "size": 351348,
      "path": "/signaturedocs/one-page.docx"
    },
    {
      "name": "password-protected.docx",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:35:40+00:00",
      "size": 10240,
      "path": "/signaturedocs/password-protected.docx"
    },
    {
      "name": "sample.mpp",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:29:10+00:00",
      "size": 289792,
      "path": "/signaturedocs/sample.mpp"
    },
    {
      "name": "three-layouts.dwf",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:26:42+00:00",
      "size": 15433,
      "path": "/signaturedocs/three-layouts.dwf"
    },
    {
      "name": "two-hidden-pages.vsd",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:17:36+00:00",
      "size": 457728,
      "path": "/signaturedocs/two-hidden-pages.vsd"
    },
    {
      "name": "uses-custom-font.pptx",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:32:30+00:00",
      "size": 39823,
      "path": "/signaturedocs/uses-custom-font.pptx"
    },
    {
      "name": "with-hidden-rows-and-columns.xlsx",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:17:37+00:00",
      "size": 15986,
      "path": "/signaturedocs/with-hidden-rows-and-columns.xlsx"
    }
  ]
}


 ```






## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-signature-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-signature-cloud), it hides the [Folder API](https://apireference.groupdocs.cloud/signature/#/Folder) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.
|---|---|---|---|---|---

### SDK Examples ###





 C#




{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Get_Files_List.cs >}}







 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Get_Files_List.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Get_Files_List.php >}}







 Ruby




{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Get_Files_List.rb >}}







 Node




{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Get_Files_List.js >}}







 Python




{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Get_Files_List.py >}}









# Create a New Folder #

This API allows you to create a new Folder in the specified Cloud Storage. If you do not pass storage name API will create new Folder in default Cloud Storage.

## API Explorer ##

[GroupDocs.signature Cloud API Reference](https://apireference.groupdocs.cloud/signature/) lets you to try out [Create Folder API](https://apireference.groupdocs.cloud/signature/#/Folder/CreateFolder) right away in your browser. It allows you to effortlessly interact and try out every single operation that our APIs exposes.
|---|---|---|---


#### Request parameters ####

|Parameter|Description
|---|---
|**path**|Target folder’s path e.g. Folder1/Folder2/. The folders will be created recursively

Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used


## cURL Example ##





 Request

```html 
curl -X POST "https://api.groupdocs.cloud/v2.0/signature/storage/folder/signaturedocs?storageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"

 ```




 Response

```html 
{  
  "code": 200,
  "status": "OK"
}
 ```






## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-signature-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-signature-cloud), it hides the [Folder API](https://apireference.groupdocs.cloud/signature/#/Folder/) calls and lets you use GroupDocs for Cloud features in a native way for your preferred language.
|---|---|---|---|---|---

### SDK Examples ###





 C#




{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Create_Folder.cs >}}







 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Create_Folder.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Create_Folder.php >}}







 Ruby




{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Create_Folder.rb >}}







 Node




{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Create_Folder.js >}}







 Python




{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Create_Folder.py >}}









# Delete a Particular Folder #

This API allows you to delete a particular Folder in the specified Cloud Storage. If you do not pass storage name API will create new Folder in default Cloud Storage. To remove recursively inner folder/files you need to pass true value to recursive parameter in Request. If it is set to false and folder contains data then API throws the exception.

## API Explorer ##

[GroupDocs.signature Cloud API Reference](https://apireference.groupdocs.cloud/signature/#/) lets you to try out [Delete a Particular Folder API](https://apireference.groupdocs.cloud/signature/#/Folder/DeleteFolder) right away in your browser. It allows you to effortlessly interact and try out every single operation that our APIs exposes. 
|---|---|---|---


#### Request parameters ####

|Parameter|Description
|---|---
|**path**|Folder path e.g. /Folder1

Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used


## cURL Example ##





 Request

```html 
curl -X DELETE "https://api.groupdocs.cloud/v2.0/signature/storage/folder/signaturedocs3?storageName#MyStorage&#x26;recursive#true" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"

 ```




 Response

```html 
{  
  "code": 200,
  "status": "OK"
}
 ```






## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-signature-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-signature-cloud), it hides the [Delete Folder API](https://apireference.groupdocs.cloud/signature/#/Folder/DeleteFolder) calls and lets you use GroupDocs for Cloud features in a native way for your preferred language.
|---|---|---|---|---|---

### SDK Examples ###





 C#




{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Delete_Folder.cs >}}







 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Delete_Folder.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Delete_Folder.php >}}







 Ruby




{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Delete_Folder.rb >}}







 Node




{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Delete_Folder.js >}}







 Python




{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Delete_Folder.py >}}









# Copy Specific Folder #

This API allows you to copy a Folder to another location in the GroupDocs Cloud Storage. If you do not pass source and destination storage names API will copy Folder within default Cloud Storage.

## API Explorer ##

[GroupDocs.signature Cloud API Reference](https://apireference.groupdocs.cloud/signature/#/) lets you to try out [Copy Folder API](https://apireference.groupdocs.cloud/signature/#/Folder/CopyFolder) right away in your browser. It allows you to effortlessly interact and try out every single operation that our APIs exposes.
|---|---|---|---

#### Request parameters ####

|Parameter|Description
|---|---
|**srcPath**|Source folder path e.g. /Folder1

Required. Can be passed as query string parameter or as part of the URL
|**destPath**|Destination folder path. Required
|srcStorageName|Name of the storage of source folder. If not set, then default storage used
|destStorageName|Name of the storage of destination folder. If not set, then default storage used


## cURL Example ##





 Request

```html 
curl -X PUT "https://api.groupdocs.cloud/v2.0/signature/storage/folder/copy/signaturedocs?destPath#signaturedocs1&#x26;srcStorageName#MyStorage&#x26;destStorageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"

 ```




 Response

```html 
{  
  "code": 200,
  "status": "OK"
}
 ```






## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-signature-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-signature-cloud), it hides the [Copy Folder API](https://apireference.groupdocs.cloud/signature/#/Folder/CopyFolder) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.
|---|---|---|---|---|---

### SDK Examples ###





 C#




{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Copy_Folder.cs >}}







 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Copy_Folder.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Copy_Folder.php >}}







 Ruby




{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Copy_Folder.rb >}}







 Node




{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Copy_Folder.js >}}







 Python




{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Copy_Folder.py >}}









# Move a Specific Folder #

This API allows you to move a Folder to another location in the GroupDocs Cloud Storage. If you do not pass source and destination storage names API will move Folder within default Cloud Storage.

## API Explorer ##

[GroupDocs.signature Cloud API Reference](https://apireference.groupdocs.cloud/signature/#/) lets you to try out [Move a Folder API](https://apireference.groupdocs.cloud/signature/#/Folder/MoveFolder) right away in your browser. It allows you to effortlessly interact and try out every single operation that our APIs exposes.
|---|---|---|---

#### Request parameters ####

|Parameter|Description
|---|---
|**srcPath**|Source folder path e.g. /Folder1

Required. Can be passed as query string parameter or as part of the URL
|**destPath**|Destination folder path. Required
|srcStorageName|Name of the storage of source folder. If not set, then default storage used
|destStorageName|Name of the storage of destination folder. If not set, then default storage used


## cURL Example ##





 Request

```html 
curl -X PUT "https://api.groupdocs.cloud/v2.0/signature/storage/folder/move/signaturedocs?destPath#signaturedocs1&#x26;srcStorageName#MyStorage&#x26;destStorageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"  
 ```




 Response

```html 
{  
  "code": 200,
  "status": "OK"
}
 ```






## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-signature-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-signature-cloud), it hides the [Move Folder API](https://apireference.groupdocs.cloud/signature/#/Folder/MoveFolder) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.
|---|---|---|---|---|---

### SDK Examples ###





 C#




{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Move_Folder.cs >}}







 Java




{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Move_Folder.java >}}







 PHP




{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Move_Folder.php >}}







 Ruby




{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Move_Folder.rb >}}







 Node




{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Move_Folder.js >}}







 Python




{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Move_Folder.py >}}







