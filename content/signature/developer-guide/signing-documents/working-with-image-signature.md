---
id: "working-with-image-signature"
url: "signature/working-with-image-signature"
title: "Working with Image Signature"
productName: "GroupDocs.Signature Cloud"
weight: 3
description: ""
keywords: ""
---

{{< alert style="info" >}}
Note:  The features listed on this page are supported only in GroupDocs.Signature Cloud V1
{{< /alert >}}










# Introduction #

GroupDocs.Signature Cloud REST API supports to sign a document with Image. It provides methods to create Image Signature in Document Pages with different options of Image name, location, alignment, font, margins and appearances by using [signature-options-objects]({{< ref "signature/developer-guide/common-resources/signature-options-objects.md" >}}) object data in request body.

# Add Image Signature to Document #

You can create image Signature on Document provided by fileName and document folder (if required) using following API. It expects [signature-options-objects]({{< ref "signature/developer-guide/common-resources/signature-options-objects.md" >}}) data in request body.

It returns an object which contains document name, location and command result.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add Image signature to a document](https://apireference.groupdocs.cloud/signature/#!/Signing/PostImage).

## cURL Example ##





 Request

```html 
curl -v "https://api.groupdocs.cloud/v1/signature/one-page.docx/image" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d "{"ImageGuid": "signature.jpg","Left": 10,"Top": 10,"Width": 40,"Height": 10,"LocationMeasureType": "Percents","SizeMeasureType": "Percents","RotationAngle": 0,"HorizontalAlignment": "Right","VerticalAlignment": "Bottom","Margin":{"All": 10,"Left": 10,"Top": 10,"Right": 10,"Bottom": 10},"MarginMeasureType": "Percents","Opacity": 1.0,"SignAllPages": true,"DocumentPageNumber": 1,"OptionsType": "WordsSignImageOptionsData"}" \
-H "authorization: Bearer rf1Wyp3-Cz_xukjKqvzF-OMwYvhJcl0rJ6CQ0IgQbZwdSGTKYJziBpGNeDdzGSwwXgsRLCCfPLhHJBKPv8dzqX3tGA8n8SA4tXhLdnGh-hws2gQgmCWEjF0RpzEdJA6jh6tGZyOSAa2GlTrLhuflBwjMB5-dc8JwRmI-ssOiXkO3fSRxnwWuWih24Co8-n8elsun4HxZVMqCzXepAiXBV9UBeUktV_PLclri_lTJEnDzoJRzfRyDigjb2-luODo9aX8DFseboggoCIMKDoyLPSVHnFXgs5EWV2aQ_DgRm_D6UPn2T1Gn7OAIe-T8aA7ypDCoR-wuTJdB8o7T0f2I8K-8FrXCy2Sgb8B5QPpAOcLdiBBqFxRdk8f2c67J-rSbm2WUPWK65pbLa8NGHHdIRKuiI87NmphWuKc39a_zcgEg4MnHSlDeephmStnLS8OayQObNdLQBYAmoeQeVpZRy9t9bcU"

 ```




 Response

```html 
{
  "fileName": "one-page.docx",
  "folder": "Output",
  "code": 200,
  "status": "OK"
}
 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Add Image Signature to Document ###





 C#




{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Signature_Image.cs >}}







 PHP




{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_Image.php >}}







 Java




{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Signature_Image.java >}}







 Python




{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Signature_Image.py >}}







 Ruby




{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Signature_Image.rb >}}









# Add Image Signature to Document at Provided URL #

You can creates Image Signature for document at provided URL with [signature-options-objects]({{< ref "signature/developer-guide/common-resources/signature-options-objects.md" >}}). It retrieves file from specified URL and tries to detect file type when fileName parameter is not specified. It saves retrieved file in storage, by using fileName and folder parameters to specify desired file name and folder to save file. When file with specified name already exists in storage new unique file name will be used for file. It expects [Signature Options Object]({{< ref "signature/developer-guide/common-resources/signature-options-objects.md" >}}) object data in request body and returns object which contains document name,folder location and command status.

## Resource ##

The following GroupDocs.Signature Cloud REST API resource has been used in the example [to add Image signature to a document at provided URL](https://apireference.groupdocs.cloud/signature/#!/Signing/PostImageFromUrl).

## cURL Example ##





 Request

```html 
curl -v "https://api.groupdocs.cloud/v1/signature/image?fileName#piechartsigned.docx&#x26;url#https%3A%2F%2Fwww.dropbox.com%2Fs%2Fbzx1xm68zd0c910%2FPieChart.docx" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d "{"ImageGuid": "signature.jpg","Left": 10,"Top": 10,"Width": 40,"Height": 10,"LocationMeasureType": "Percents","SizeMeasureType": "Percents","RotationAngle": 0,"HorizontalAlignment": "Right","VerticalAlignment": "Bottom","Margin":{"All": 10,"Left": 10,"Top": 10,"Right": 10,"Bottom": 10},"MarginMeasureType": "Percents","Opacity": 1.0,"SignAllPages": true,"DocumentPageNumber": 1,"OptionsType": "WordsSignImageOptionsData"}" \
-H "authorization: Bearer rf1Wyp3-Cz_xukjKqvzF-OMwYvhJcl0rJ6CQ0IgQbZwdSGTKYJziBpGNeDdzGSwwXgsRLCCfPLhHJBKPv8dzqX3tGA8n8SA4tXhLdnGh-hws2gQgmCWEjF0RpzEdJA6jh6tGZyOSAa2GlTrLhuflBwjMB5-dc8JwRmI-ssOiXkO3fSRxnwWuWih24Co8-n8elsun4HxZVMqCzXepAiXBV9UBeUktV_PLclri_lTJEnDzoJRzfRyDigjb2-luODo9aX8DFseboggoCIMKDoyLPSVHnFXgs5EWV2aQ_DgRm_D6UPn2T1Gn7OAIe-T8aA7ypDCoR-wuTJdB8o7T0f2I8K-8FrXCy2Sgb8B5QPpAOcLdiBBqFxRdk8f2c67J-rSbm2WUPWK65pbLa8NGHHdIRKuiI87NmphWuKc39a_zcgEg4MnHSlDeephmStnLS8OayQObNdLQBYAmoeQeVpZRy9t9bcU"
 
 ```




 Response

```html 
{
  "fileName": "PieChart.docx",
  "folder": "Output",
  "Code": 200,
  "Status" : "OK"
}
 ```






## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### Add Image Signature to Document at specified URL ###





 C#




{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Signature_Image_URL.cs >}}







 PHP




{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Signature_Image_URL.php >}}







 Java




{{< gist groupdocscloud d95398adbee451da9981705cf5c6ad7f Signature_Java_Signature_Image_URL.java >}}







 Python




{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Signature_Image_URL.py >}}







 Ruby




{{< gist groupdocscloud 1a0d1223161ccb6a2157dcef82c39c37 Signature_Ruby_Signature_Image_URL.rb >}}







