---
description: Information about Amazon Simple Storage Service (Amazon S3).
seo-description: Information about Amazon Simple Storage Service (Amazon S3).
seo-title: Amazon S3  About
solution: Audience Manager
title: Amazon S3  About
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: Reference
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
---
# Amazon S3: About{#amazon-s-about}

Information about Amazon Simple Storage Service (Amazon S3).

As best practice, we recommend using Amazon S3 instead of FTP as a method for getting files from and delivering files to partners. Amazon S3 provides a simple web services interface that can be used to store and retrieve any amount of data, at any time, from anywhere on the web.

The benefits of using Amazon S3 include:

* **Scalability:** Amazon S3 provides almost limitless scalability. 
* **Reliability and Availability:** Amazon S3 provides high durability and high availability storage services. 
* **Speed:** Amazon S3 allows fast data transfers. 
* **Ease of Use:** Amazon S3 is very easy to use and to implement. Your implementation can be up and running in about an hour. Implementing a FTP directory takes much longer. 
* **Multi-Part Uploads:** Large files can be uploaded quickly and efficiently as multi-part file uploads. 
* **Security:** Amazon S3 provides strong security.

    * All directories are accessible only to the appropriate customer or client. 
    * HTTPS protocol support for uploads and downloads. You should always use HTTPS when transferring files in [!DNL Audience Manager]. 
    * Amazon S3 provides encryption-at-rest for encrypting [outbound data files](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). We use the [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) encryption method, which allows encryption keys to be automatically generated and managed by Amazon S3.

* **Debug and Backup Support:** Amazon S3 allows [!DNL Audience Manager] to retain exact copies of files to make debugging or re-transfers easier.

For more information about Amazon S3, see the following resources:

[Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/) on the Amazon Web Services website.

[Get Started with Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) on the AWS Documentation website.
