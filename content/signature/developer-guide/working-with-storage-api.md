---
id: "working-with-storage-api"
url: "signature/working-with-storage-api"
title: "Working with Storage API"
productName: "GroupDocs.Signature Cloud"
weight: 10
description: ""
keywords: ""
---

# Storage existence API #

This API intended for checking existence of cloud storage with given name from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud).

## API Explorer ##

[GroupDocs.Signature Cloud API Reference](https://apireference.groupdocs.cloud/signature/#/) lets you to try out [Storage existence API](https://apireference.groupdocs.cloud/signature/#/Storage/StorageExists) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

### Request parameters ###

|Parameter|Description
|---|---
|**storageName**|Storage name

## cURL Example ##

Request

```html
curl -X GET "https://api.groupdocs.cloud/v2.0/signature/storage/MyStorage/exist" -H  "accept: application/json" -H  "authorization: Bearer  [Access Token]"
```

Response

```html
{
  "exists": true
}
```

## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-conversion-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-conversion-cloud), it hides the [Storage existence](https://apireference.groupdocs.cloud/signature/#/Storage/StorageExists) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

### SDK Examples ###

C#

{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Storage_Exist.cs >}}

Java

{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Storage_Exist.java >}}

PHP

{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Storage_Exist.php >}}

Ruby

{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Storage_Exist.rb >}}

Node

{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Storage_Exist.js >}}

Python

{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Storage_Exist.py >}}

# Storage object existence API #

This API intended for checking existence of file or folder in [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud).

## API Explorer ##

[GroupDocs.Signature Cloud API Reference](https://apireference.groupdocs.cloud/signature/#/) lets you to try out [Storage Object existence API](https://apireference.groupdocs.cloud/signature/#/Storage/StorageExists) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

### Request parameters ###

|Parameter|Description
|---|---
|**path**|Path of the file or folder

Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used
|versionId|File version id

## cURL Example ##

Request

```html
curl -X GET "https://api.groupdocs.cloud/v2.0/signature/storage/exist/signaturedocs?storageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
 ```

Response

```html
{
  "exists": true,
  "isFolder": true
}
 ```

## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-conversion-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-conversion-cloud), it hides the [Storage Object existence](https://apireference.groupdocs.cloud/signature/#/Storage/ObjectExists) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

### SDK Examples ###

C#

{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Object_Exists.cs >}}

Java

{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Object_Exists.java >}}

PHP

{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Object_Exists.php >}}

Ruby

{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Object_Exists.rb >}}

Node

{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Object_Exists.js >}}

Python

{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Object_Exists.py >}}

# Storage Space Usage API #

This API intended for getting total and used space of the[ GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud)

## API Explorer ##

[GroupDocs.Signature Cloud API Reference](https://apireference.groupdocs.cloud/signature/#/) lets you to try out [storage space usage API](https://apireference.groupdocs.cloud/signature/#/Storage/GetDiscUsage) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

### Request parameters ###

|Parameter|Description
|---|---
|storageName|Name of the storage. If not set, then default storage used

## cURL Example ##

Request

```html
curl -X GET "https://api.groupdocs.cloud/v2.0/signature/storage/disc?storageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
```

Response

```html
{
  "usedSize": 31032368,
  "totalSize": 3221225472
}
```

## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-conversion-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-conversion-cloud), it hides the [storage space usage API](https://apireference.groupdocs.cloud/conversion/#/Storage/GetDiscUsage) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

### SDK Examples ###

C#

{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Get_Disc_Usage.cs >}}

Java

{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Get_Disc_Usage.java >}}

PHP

{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Get_Disc_Usage.php >}}

Ruby

{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Get_Disc_Usage.rb >}}

Node

{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Get_Disc_Usage.js >}}

Python

{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Get_Disc_Usage.py >}}

# Storage File Versions API #

This API intended for getting the list of file versions, stored in the [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud)

## API Explorer ##

[GroupDocs.Signature Cloud API Reference](https://apireference.groupdocs.cloud/signature/#/) lets you to try out [Storage File Versions API](https://apireference.groupdocs.cloud/signature/#/Storage/GetFileVersions) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

### Request parameters ###

|Parameter|Description
|---|---
|**path**|Path of the file including file name and extension e.g. /Folder1/file.ext Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used

## cURL Example ##

Request

```html
curl -X GET "https://api.groupdocs.cloud/v2.0/signature/storage/version/one-page.docx?storageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
 ```

Response

```html
{
  "value": [
    {
      "versionId": "null",
      "isLatest": true,
      "name": "one-page.docx",
      "isFolder": false,
      "modifiedDate": "2018-08-16T19:45:05+00:00",
      "size": 347612,
      "path": "/one-page.docx"
    }
  ]
}
 ```

## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-conversion-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-conversion-cloud), it hides the [Storage File Versions API](https://apireference.groupdocs.cloud/conversion/#/Storage/GetFileVersions) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

### SDK Examples ###

C#

{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Get_File_Versions.cs >}}

 Java

{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Get_File_Versions.java >}}

PHP

{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Get_File_Versions.php >}}

Ruby

{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Get_File_Versions.rb >}}

Node

{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Get_File_Versions.js >}}

Python

{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Get_File_Versions.py >}}
