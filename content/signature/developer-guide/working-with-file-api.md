---
id: "working-with-file-api"
url: "signature/working-with-file-api"
title: "Working with File Api"
productName: "GroupDocs.Signature Cloud"
weight: 2
description: ""
keywords: ""
---

# Download File API #

This API allows you to download a file from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud).

## API Explorer ##

[GroupDocs.signatureCloud API Reference](https://apireference.groupdocs.cloud/signature/#/) lets you to try out [Download a File API](https://apireference.groupdocs.cloud/signature/#/File/DownloadFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

### Request parameters ###

|Parameter|Description
|---|---
|**Path**|Path of the file including file name and extension e.g. /Folder1/file.ext Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used
|versionId|File version id

## cURL Example ##

 Request

```javascript
curl -X GET "https://api.groupdocs.cloud/v2.0/signature/storage/file/one-page.docx?storageName#MyStorage" -H  "accept: multipart/form-data" -H  "authorization: Bearer [Access Token]"

```

 Response

```javascript
{
  "Code": 200,
  "Status": "OK"
}

```

## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-signature-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-signature-cloud), it hides the [File API](https://apireference.groupdocs.cloud/signature/#/) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

### SDK Examples ###

C#

{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Download_File.cs >}}

Java

{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Download_File.java >}}

PHP

{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Download_File.php >}}

Ruby

{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Download_File.rb >}}

Node

{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Download_File.js >}}

Python

{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Download_File.py >}}

#  Upload File API #

This API allows you to upload files to the [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud/).

## API Explorer ##

[GroupDocs.signatureCloud API Reference](https://apireference.groupdocs.cloud/signature/#/) lets you try out [Upload a File API](https://apireference.groupdocs.cloud/signature/#/File/UploadFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

### Request Body parameters ###

|Parameter|Description
|---|---
|**path**|Path of the file including file name and extension e.g. /Folder1/file.ext Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used
|File|File content

## cURL Example ##

Request

```javascript
curl -X POST "https://api.groupdocs.cloud/v2.0/signature/storage/file/signaturedocs%2Fone-page2.docx?storageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"

```

Response

```javascript
Http status code: 200 (Returns OK and list of errors, which is empty if success.)
{
  "Uploaded": [
    "string"
  ],
  "Errors": [
    {
      "Code": "string",
      "Message": "string",
      "Description": "string",
      "InnerError": {
        "RequestId": "string",
        "Date": "2019-02-27T06:10:08.884Z"
      }
    }
  ]
}

```

## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-signature-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-signature-cloud), it hides the [File API](https://apireference.groupdocs.cloud/signature/#/File) calls and lets you use GroupDocs for Cloud features in a native way for your preferred language.

### SDK Examples ###

C#

{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Upload_File.cs >}}

Java

{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Upload_File.java >}}

PHP

{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Upload_File.php >}}

Ruby

{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Upload_File.rb >}}

Node

{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Upload_File.js >}}

Python

{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Upload_File.py >}}

# Delete File API #

This API allows you to delete specific file from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud/).

## API Explorer ##

[GroupDocs.signaturefor Cloud API Reference](https://apireference.groupdocs.cloud/signature/#/) lets you to try out [Delete a File](https://apireference.groupdocs.cloud/signature/#/File/DeleteFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

### Request parameters ###

|Parameter|Description
|---|---
|**path**|Path of the file including file name and extension e.g. /Folder1/file.ext Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used
|versionId|File version id

## cURL Example ##

Request

```javascript
curl -X DELETE "https://api.groupdocs.cloud/v2.0/signature/storage/file/signaturedocs1%2Fone-page1.docx?storageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"

```

Response

```javascript
{
  "Code": 200,
  "Status": "OK"
}

```

## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-signature-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-signature-cloud), it hides the [File API](https://apireference.groupdocs.cloud/signature/#/File) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

### SDK Examples ###

C#

{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Delete_File.cs >}}

Java

{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Delete_File.java >}}

PHP

{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Delete_File.php >}}

Ruby

{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Delete_File.rb >}}

Node

{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Delete_File.js >}}

Python

{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Delete_File.py >}}

# File Copy API #

This API allows you to copy specific file from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud/).

## API Explorer ##

[GroupDocs.signature for Cloud API Reference](https://apireference.groupdocs.cloud/signature/#/) lets you to try out [Copy File](https://apireference.groupdocs.cloud/signature/#/File/CopyFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

###  Request parameters ###

|Parameter|Description
|---|---
|**srcPath**|Path of the source file including file name and extension e.g. /Folder1/file.ext Required. Can be passed as query string parameter or as part of the URL
|**destPath**|Path of the destination file. Required.
|srcStorageName|Name of the storage of source file. If not set, then default storage used
|destStorageName|Name of the storage of destination file. If not set, then default storage used
|versionId|Source file version id

## cURL Example ##

Request

```javascript
curl -X PUT "https://api.groupdocs.cloud/v2.0/signature/storage/file/copy/sinaturedocs%2Fone-page1.docx?destPath#sinaturedocs%2Fone-page1.docx'&#x26;srcStorageName#MyStorage&#x26;destStorageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"

```

Response

```javascript
{
  "Code": 200,
  "Status": "OK"
}

```

## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-signature-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-signature-cloud), it hides the [File API](https://apireference.groupdocs.cloud/signature/#/File) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

### SDK Examples ###

C#

{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Copy_File.cs >}}

Java

{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Copy_File.java >}}

PHP

{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Copy_File.php >}}

Ruby

{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Copy_File.rb >}}

Node

{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Copy_File.js >}}

Python

{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Copy_File.py >}}

# File Move API #

This API allows you to copy specific file from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud/).

## API Explorer ##

[GroupDocs.Signaturefor Cloud API Reference](https://apireference.groupdocs.cloud/signature/#/) lets you to try out [Move File](https://apireference.groupdocs.cloud/signature/#/File/MoveFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

###  Request parameters ###

|Parameter|Description
|---|---
|**srcPath**|Path of the source file including file name and extension e.g. /Folder1/file.ext Required. Can be passed as query string parameter or as part of the URL
|**destPath**|Path of the destination file. Required.
|srcStorageName|Name of the storage of source file. If not set, then default storage used
|destStorageName|Name of the storage of destination file. If not set, then default storage used
|versionId|Source file version id

## cURL Example ##

Request

```javascript
curl -X PUT "https://api.groupdocs.cloud/v2.0/signature/storage/file/move/sinaturedocs%2Fone-page1.docx?destPath#sinaturedocs%2Fone-page1.docx'&#x26;srcStorageName#MyStorage&#x26;destStorageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"

```

Response

```javascript
{
  "Code": 200,
  "Status": "OK"
}
```

## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-signature-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-signature-cloud), it hides the [File API](https://apireference.groupdocs.cloud/signature/#/File) calls and lets you use GroupDocs for Cloud features in a native way for your preferred language.

### SDK Examples ###

C#

{{< gist groupdocscloud 930234f9ab12e6e3a5b7cfeb98928c9d Signature_CSharp_Move_File.cs >}}

Java

{{< gist groupdocscloud d752cfd742c8869fa25ef531a9e29236 Signature_Java_Move_File.java >}}

PHP

{{< gist groupdocscloud 4d51ebda15c88dcc9da36b902fffc8a8 Signature_Php_Move_File.php >}}

Ruby

{{< gist groupdocscloud 37b171abdcc6961eab45170e66037696 Signature_Ruby_Move_File.rb >}}

Node

{{< gist groupdocscloud 39c386004ccdadc059d6cc7124ebb77e Signature_Node_Move_File.js >}}

Python

{{< gist groupdocscloud 371ae0feb03d6df33ec242272ccf7112 Signature_Python_Move_File.py >}}
