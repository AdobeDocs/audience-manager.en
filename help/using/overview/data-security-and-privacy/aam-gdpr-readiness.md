---
description: GDPR Readiness Guidance for Audience Manager Customers
seo-description: GDPR Readiness Guidance for Audience Manager Customers
seo-title: GDPR Readiness Guidance for Audience Manager Customers
solution: Audience Manager
title: GDPR Readiness Guidance for Audience Manager Customers
feature: Data Governance & Privacy
exl-id: 353b9035-20f3-41ff-819c-71f161e6b1e1
TQID: https://experienceleague.adobe.com/K72pQ8Q6yILWexkG38Hc5W1roYObFvhLE5A0GSCyhYE
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: c814092e-2730-45e8-a12d-e084529f52cb
    internal-label: Destinations
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
    internal-label: Administration
subfeature_v2:
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
    internal-label: Overview
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# GDPR Readiness Guidance for Audience Manager Customers (Data Controllers) {#gdpr-readiness-guidance}

Audience Manager recommends being proactive in the areas of data governance and organizational readiness. This will help you ensure that your consumer data will be organized for processes related to access or delete requests, your teams will be enabled and empowered to manage these requests, and your consumers (Data Subjects) will have a positive, differentiated experience with your brand.

As your Data Processor, Adobe cannot provide legal advice on GDPR requirements and the process for obtaining consent from your Data Subjects. Please consult your legal counsel for guidance on GDPR compliance for your organization.

## Data Governance: Start thinking about how your consumer data is managed in your in Audience Manager instance

* Review the various customer IDs your marketing teams use to identify users in Audience Manager, along with the data sources in which they are stored. This will streamline the process for requests (such as delete or access) since certain data types will be hashed by your teams prior to ingestion in Audience Manager.
* IDFA/GAID mobile device IDs are used for multiple use cases in Audience Manager. If you are using Adobe Mobile SDK, please make sure to submit the Experience Cloud ID (MID) along with IDFA/GAID to make sure the GDPR responses are complete.
* With the definition of personal data becoming more expansive, IP addresses may be considered personal data in your region. Proactively engage with Adobe Consulting to obfuscate the last octet.
* Determine a validation/authentication policy & process for confirming the identity of a Data Subject when they make a GDPR request.
* Consider using [Data Export Controls](../../features/data-export-controls.md) to block audience activation to technologies that house personal data. For example, segments with third-party data should not syndicated to email service providers. Set a [!UICONTROL Data Export Control] to ensure that no one in your organization can accidentally activate this data.
* Begin utilizing [Role Based Access Controls](../../features/administration/administration-overview.md) to ensure the right teams have access to intended data.
* Consider appropriate [retention periods](../../faq/faq-privacy.md#data-retention-faq) for the data.
* Review identity linkage and privacy policies and legal requirements to see when and where it is appropriate to tie identity sets together; use appropriately via Audience Manager’s [Profile Merge Rules](../../features/profile-merge-rules/merge-rules-overview.md).

## Organizational Readiness: Establish a business process

* Identify a process to receive/respond to Data Subject requests. Consider building an automated tool to submit requests to Audience Manager.
* Appoint a privacy point of contact within your DMP center of excellence. Connect your organization’s privacy point of contact with your Audience Manager product usage team to understand how you might manage your input ID requirements.
* Conduct a data review prior to sharing with the Data Subject. Document the steps you put in place, to help you establish accountability.
