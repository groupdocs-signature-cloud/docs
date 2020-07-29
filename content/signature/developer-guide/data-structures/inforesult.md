---
id: "inforesult"
url: "signature/inforesult"
title: "InfoResult"
productName: "GroupDocs.Signature Cloud"
weight: 3
description: ""
keywords: ""
---

# InfoResult #

InfoResult data structure returned by  as output result

##### InfoResult example #####

```html 

{
    "pages": [
        {
            "number": 1,
            "width": 100,
            "height": 200
        },
        {
            "number": 2,
            "width": 0,
            "height": 0
        }
    ]
}

 ```

##### InfoResult fields #####

|Name|Description
|---|---
|pages|List of document pages
|page.number|Page number, starts from 1
|page.width|Page width, if image format requested, otherwise 0
|page.height|Page height, if image format requested, otherwise 0

