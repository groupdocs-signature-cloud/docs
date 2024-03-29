---
id: "supported-qr-codes"
url: "signature/supported-qr-codes"
title: "Supported QR-Codes"
productName: "GroupDocs.Signature Cloud"
weight: 6
description: ""
keywords: ""
toc: True
---

{{< alert style="info" >}}
Note:  The features listed on this page are supported only in GroupDocs.Signature Cloud V1
{{< /alert >}}

GroupDocs.Signature Cloud REST API supports to sign a document with QR-Code. You can list all supported QR-Ccode types using this API.

## Resource

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to list supported QR-Code types](https://apireference.groupdocs.cloud/signature/#!/Helper/GetQRCodes).

## cURL example

{{< tabs "example1">}} {{< tab "Request" >}}

```javascript
curl -v "https://api.groupdocs.cloud/v1/signature/qrcodes" \
-X GET \
-H "Content-Type: application/json" \
-H "authorization: Bearer _0zqJ6w3enMdpEw5C6ZKm3lgYvHell1lHdx3vztekvBpCbZGqMvMplrKNrsVXih9Xe6738GSej2hb0BnwKVVz-ANEOnW0bGqjeiJcEySo2Y9-9VZ1K_rs_p4zZcsMoGNuDkL9G4rowGX9Wd1frChwRXzsJCpJUs9G5fGK-0kochaFTVdMgoOHU8JjUOQ5wiu-_ZQSbR0bMKRamxEyc_P_gv9NU7LTJQTCrP1SIJwem1WTX7GaTr8JRUYE0zsXH2vHUkJ1rNh-1RPblqE6wwrfxkklTCGxAWTxvoaSG-Ax-h2Zl9nZkBCAjS48zzz2kqIWS-K5WUmGPP9hAWQL00_deMB0Qi7xqvf2MWoJ831mFnyse-ZQ80fAqPyFBdYpS-xVFC0Uuc8rVHehydCxD0_oIJWkCU_GuDJpNMv6q4IpM-1RzFn"

```

{{< /tab >}} {{< tab "Response" >}}

```javascript
{
  "qrCodeTypes": [
    {
      "name": "Aztec"
    },
    {
      "name": "DataMatrix"
    },
    {
      "name": "GS1DataMatrix"
    },
    {
      "name": "GS1QR"
    },
    {
      "name": "QR"
    }
  ]
}
```

{{< /tab >}} {{< /tabs >}}

## SDK examples

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](/signature/available-sdks).

{{< tabs "example2">}} {{< tab "C#" >}}

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Supported_QRcodes.cs >}}

{{< /tab >}} {{< tab "Java" >}}

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Supported_QRcodes.java >}}

{{< /tab >}} {{< tab "Python" >}}

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Supported_QRcodes.py >}}

{{< /tab >}} {{< tab "Ruby" >}}

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Supported_QRcodes.rb >}}

{{< /tab >}} {{< /tabs >}}
