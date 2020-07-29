---
id: "quick-start"
url: "signature/quick-start"
title: "Quick Start"
productName: "GroupDocs.Signature Cloud"
weight: 3
description: ""
keywords: ""
---






# Create an account #

Creating an account is very simple. Go to [https://dashboard.groupdocs.cloud](https://dashboard.groupdocs.cloud/#/) to create a free account. 

# Create an API client app #

Before you can make any requests to GroupDocs for Cloud API you need to get APP SID and APP key (secret key). This will will be used to invoke GroupDocs for Cloud API. 

You can get it from default Application or create new Application from [My Apps tab of GroupDocs for Cloud Dashboard]({{< ref "total/getting-started/ui-topics/create-new-app-and-get-app-key-and-sid.md" >}}).

# Install the SDK of your choice #

GroupDocs for Cloud SDK is written in different languages, all you need to get started is adding our [SDK]({{< ref "signature/getting-started/available-sdks.md" >}}) to your existing project.

# Make an API request from the SDK of your choice #

Use the **App SID** and **App key (secret key)** from the API app client you created in step one and replace in the corresponding code. Below is an example demonstrating using the Formats API to get all supported file formats in GroupDocs.Signature Cloud.

{{< alert style="info" >}}The GitHub repository for [GroupDocs.Signature Cloud](https://github.com/groupdocs-signature-cloud) has a complete set of examples, demonstrating our API capabilities.{{< /alert >}}



 C#




{{< gist groupdocscloud e1e1480f327b6a0982bc1ecc3768718f Signature_CSharp_Supported_FileFormats.cs >}}







 PHP




{{< gist groupdocscloud a43adea6e4f64b33ea37ead904a401cb Signature_Php_Supported_FileFormats.php >}}







 Python




{{< gist groupdocscloud e967ad642d9e6e11f123064b9292e12e Signature_Python_Supported_FileFormats.py >}}







