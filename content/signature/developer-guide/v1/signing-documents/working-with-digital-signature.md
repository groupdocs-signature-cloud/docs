---
id: "working-with-digital-signature"
url: "signature/working-with-digital-signature"
title: "Working with Digital Signature"
productName: "GroupDocs.Signature Cloud"
weight: 2
description: ""
keywords: ""
---

{{< alert style="info" >}}
Note:  The features listed on this page are supported only in GroupDocs.Signature Cloud V1
{{< /alert >}}

# Introduction #

GroupDocs.Signature Cloud REST API supports to add Digital Signature to a document. It provides methods to create Digital Signature in Document Pages with different options of Certificate type, location, alignment, font, margins and appearances by using [Signature Options Object]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}) data in request body.

# Add Digital Signature to Document #

You can create Digital Signature on Document provided by fileName and document folder (if required) using following API. It expects [Signature Options Object]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}) data in request body.

It returns an object which contains document name, folder location and process result.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add Digital signature to a document](https://apireference.groupdocs.cloud/signature/#!/Signing/PostDigital).

## cURL Example ##

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}} {{< tab tabNum="1" >}}

```javascript
curl -v "https://api.groupdocs.cloud/v1/signature/01_pages.pdf/digital" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" -d "{"Visible": true,"Password": "password","CertificateGuid": "temp.pfx","ImageGuid": "signature.jpg","Left": 10,"Top": 10,"Width": 40,"Height": 10,"LocationMeasureType": "Millimeters","SizeMeasureType": "Millimeters","RotationAngle": 0,"HorizontalAlignment": "Right","VerticalAlignment": "Bottom","Margin": {"All": 10,"Left": 10,"Top": 10,"Right": 10,"Bottom": 10},"MarginMeasureType": "Millimeters","Opacity": 0.5,"SignAllPages": true,"DocumentPageNumber": 1,"OptionsType": "PdfSignDigitalOptionsData"}" \
-H "authorization: Bearer rf1Wyp3-Cz_xukjKqvzF-OMwYvhJcl0rJ6CQ0IgQbZwdSGTKYJziBpGNeDdzGSwwXgsRLCCfPLhHJBKPv8dzqX3tGA8n8SA4tXhLdnGh-hws2gQgmCWEjF0RpzEdJA6jh6tGZyOSAa2GlTrLhuflBwjMB5-dc8JwRmI-ssOiXkO3fSRxnwWuWih24Co8-n8elsun4HxZVMqCzXepAiXBV9UBeUktV_PLclri_lTJEnDzoJRzfRyDigjb2-luODo9aX8DFseboggoCIMKDoyLPSVHnFXgs5EWV2aQ_DgRm_D6UPn2T1Gn7OAIe-T8aA7ypDCoR-wuTJdB8o7T0f2I8K-8FrXCy2Sgb8B5QPpAOcLdiBBqFxRdk8f2c67J-rSbm2WUPWK65pbLa8NGHHdIRKuiI87NmphWuKc39a_zcgEg4MnHSlDeephmStnLS8OayQObNdLQBYAmoeQeVpZRy9t9bcU"

```

{{< /tab >}} {{< tab tabNum="2" >}}

```javascript
{
  "fileName": "one-page.pdf",
  "folder": "Output",
  "code": 200,
  "status": "OK"
}
{{< /tab >}} {{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Add Digital Signature to Document ###

C#

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Signature_Digital.cs >}}

PHP

{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_Digital.php >}}

Java

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Signature_Digital.java >}}

Python

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Signature_Digital.py >}}

Ruby

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Signature_Digital.rb >}}

# Add Digital Signature to Document at Provided URL #

You can creates Digital Signature for document at provided URL with [signature-options-objects]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}). It retrieves file from specified URL and tries to detect file type when fileName parameter is not specified. It saves retrieved file in storage, by using fileName and folder parameters to specify desired file name and folder to save file. When file with specified name already exists in storage new unique file name will be used for file. It expects [Signature Options Object]({{< ref "signature/developer-guide/v1/common-resources/signature-options-objects.md" >}}) data in request body and returns object which contains document name and folder location.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add Digital signature to a document at provided URL](https://apireference.groupdocs.cloud/signature/#!/Signing/PostDigitalFromUrl).

## cURL Example ##

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}} {{< tab tabNum="1" >}}

```javascript
curl -v "https://api.groupdocs.cloud/v1/signature/digital?url#https%3a%2f%2fwww.dropbox.com%2fs%2fumokluz338w4ng7%2fone-page.docx%3fdl%3d1" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" -d "{"Margin": {"All": 10,"Left": 10,"Top": 10,"Right": 10,"Bottom": 10},"DocumentPageNumber": 1,"SheetNumber": 1,"RowNumber": 1,"ColumnNumber": 2,"Password":"password","CertificateGuid":"temp.pfx","ImageGuid":"signature.jpg","Left": 1,"Top": 1,"Width": 40,"Height": 40,"LocationMeasureType": "Pixels","SizeMeasureType":"Millimeters","RotationAngle": 0,"HorizontalAlignment": "Left","VerticalAlignment": "Bottom","MarginMeasureType":"Pixels","Opacity": 0.5,"SignAllPages": true,"OptionsType": "WordsSignDigitalOptionsData"}" \
-H "authorization: Bearer rf1Wyp3-Cz_xukjKqvzF-OMwYvhJcl0rJ6CQ0IgQbZwdSGTKYJziBpGNeDdzGSwwXgsRLCCfPLhHJBKPv8dzqX3tGA8n8SA4tXhLdnGh-hws2gQgmCWEjF0RpzEdJA6jh6tGZyOSAa2GlTrLhuflBwjMB5-dc8JwRmI-ssOiXkO3fSRxnwWuWih24Co8-n8elsun4HxZVMqCzXepAiXBV9UBeUktV_PLclri_lTJEnDzoJRzfRyDigjb2-luODo9aX8DFseboggoCIMKDoyLPSVHnFXgs5EWV2aQ_DgRm_D6UPn2T1Gn7OAIe-T8aA7ypDCoR-wuTJdB8o7T0f2I8K-8FrXCy2Sgb8B5QPpAOcLdiBBqFxRdk8f2c67J-rSbm2WUPWK65pbLa8NGHHdIRKuiI87NmphWuKc39a_zcgEg4MnHSlDeephmStnLS8OayQObNdLQBYAmoeQeVpZRy9t9bcU"
 
```

{{< /tab >}} {{< tab tabNum="2" >}}

```javascript
{
  "fileName": "one-page.docx",
  "folder": "Output",
  "Code": 200,
  "Status" : "OK"
}
{{< /tab >}} {{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Add Digital Signature to Document at specified URL ###

C#

{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Signature_Digital_URL.cs >}}

PHP

{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_Digital_URL.php >}}

Java

{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Signature_Digital_URL.java >}}

Python

{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Signature_Digital_URL.py >}}

Ruby

{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Signature_Digital_URL.rb >}}

