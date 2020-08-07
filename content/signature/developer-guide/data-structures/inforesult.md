---
id: "inforesult"
url: "signature/inforesult"
title: "InfoResult"
productName: "GroupDocs.Signature Cloud"
weight: 3
description: ""
keywords: ""
---

InfoResult data structure returned by Info API method  as output result

##### InfoResult example #####

```javascript
{
  "fileInfo": {
    "filePath": "signaturedocs/one-page.docx",
    "storageName": null,
    "versionId": null,
    "password": null
  },
  "extension": "docx",
  "fileFormat": "Microsoft Word Open XML Document",
  "size": 1359584,
  "pagesCount": 1,
  "dateCreated": "2020-07-21T05:37:12.1994841Z",
  "dateModified": "2020-07-14T07:03:23Z",
  "widthForMaxHeight": 612,
  "maxPageHeight": 792,
  "pages": [
    {
      "number": 0,
      "name": null,
      "width": 612,
      "height": 792,
      "angle": 0,
      "visible": false
    }
  ]
}

```

##### InfoResult fields #####

|Name|Description
|---|---
|FileInfo|File path, storage, version, password
|Extension|Document extension
|FileFormat|Document file format
|Size|Document size in bytes
|PagesCount|Count of pages in document
|DateCreated|Document creation date
|DateModified|Document modification date
|WidthForMaxHeight|Specifies width for max height of document page
|MaxPageHeight|Specifies max page height
|pages|List of document pages
|page.number|Page number, starts from 1
|page.Name|Page name
|page.width|Page width, if image format requested, otherwise 0
|page.height|Page height, if image format requested, otherwise 0
|Angle|Page angle
|Visible|Page visibility
