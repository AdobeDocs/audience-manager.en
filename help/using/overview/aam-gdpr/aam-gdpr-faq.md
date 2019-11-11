---
description: This material contains some of the most common questions asked by our customers and partners related to the European General Data Protection Regulation (GDPR), and how Adobe Audience Manager, as a Data Processor, addresses various GDPR requirements.
seo-description: This material contains some of the most common questions asked by our customers and partners related to the European General Data Protection Regulation (GDPR), and how Adobe Audience Manager, as a Data Processor, addresses various GDPR requirements.
seo-title: GDPR FAQ
solution: Audience Manager
title: GDPR FAQ
uuid: e52cad27-6a44-45ee-8524-6080adb86cc8
---

# GDPR FAQ{#gdpr-faq}

This material contains some of the most common questions asked by our customers and partners related to the European General Data Protection Regulation (GDPR), and how Adobe Audience Manager, as a Data Processor, addresses various GDPR requirements.

In this article, we address questions on GDPR readiness in Audience Manager. Make sure you also read the [Experience Cloud GDPR FAQ.](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-faq.md)

GDPR came into effect on May 25, 2018 with primary objectives of giving individuals in the EU (Data Subjects) more control of their personal data while simplifying the regulatory environment for international businesses by better unifying regulation within the EU. As part of Adobe's GDPR readiness, the Adobe Audience Manager team has enhanced services and processes as necessary to support access and delete requests from Data Subjects, your consumers.

## GDPR Glossary {#gdpr-glossay}

Get familiar with key terms used related to GDPR. We’ve highlighted some of the most commonly used terms below.

<br>&nbsp;

**Data Controller:** GDPR defines "Controller" as “the … legal person … which alone or jointly with others determines the purposes and means of the processing of personal data.” Audience Manager customers are Data Controllers. Customers control how data is managed in Audience Manager.

<br>&nbsp;

**Data Processor:** The "Processor" is "the … legal person … which processes personal data on behalf of the controller". In the context of Audience Manager (Adobe's Data Management Platform or DMP), Adobe is acting as a “Data Processor” for any personal data it processes and stores and services via the DMP. Adobe only processes personal data in accordance with the Data Controller’s permission and instructions (for example, as set out in our agreement with the customer).

<br>&nbsp;

**Data Subject:** The individual to whom the personal data relates. In the context of Audience Manager, Data Subjects are Audience Manager customer’s consumers or end users. If Audience Manager receives requests directly from Data Subjects, these requests will be forwarded to the respective Adobe Customers.

<br>&nbsp;

**Consent:** Consent means "any freely given, specific, informed and unambiguous indication of the Data Subject’s wishes by which he or she, by a statement or by a clear affirmative action, signifies agreement to the processing of personal data relating to him or her". Consent is the responsibility of the Data Controller, not Adobe through Audience Manager.

<br>&nbsp;

**Access:** Data Subjects have the right to require the Data Controller to confirm whether the Controller processes their personal data. Where the Data Controller does process the Data Subject's personal data, it has to provide access to, and a copy of, the personal data. Data Controllers may ask Adobe to assist with access requests from Data Subjects.

<br>&nbsp;

**Delete:** GDPR outlines the “Right to be forgotten” or “Right to Erasure.” Data Subjects have the right to require Data Controllers to erase their personal data. Data Controllers work with their Processors, including Adobe, to support delete requests from Data Subjects.

<br>&nbsp;

**Correction:** Data Subjects have the right to require Data Controllers to rectify inaccurate personal data. Data Controllers work with Processors, including Adobe, to support Correction requests from Data Subjects.

<br>&nbsp;

**Audience Manager Identifiers (IDs):** Adobe Audience Manager stores various types of IDs. The [GDPR in Audience Manager](../data-security-and-privacy/privacy-regulations-compliance.md#aam-ids) page provides a summary of these IDs, their corresponding data sources, and brief descriptions. When providing requests to Adobe, reference these IDs to make delete or access requests for your data subjects.

<br>&nbsp;

**Personal Data:** GDPR expands the definition of personal data. Under GDPR, any data in Audience Manager can be classified as personal data depending on customer use case.

<br>&nbsp;

**Prohibited Data:** Audience Manager prohibits customers from ingesting directly identifiable information such as first name and last name, email ID, CRM ID, which can be used to directly identify an individual. Adobe Experience Cloud solutions also prohibit sensitive information. Please refer to your contract with Adobe for details about these requirements. If these types of data points need to be ingested into Audience Manager, consult your Adobe consulting team for recommendations on hashing these IDs before ingestion.

<br>&nbsp;

## Managing Individual GDPR Rights {#manage-ind-gdpr-rights}

**Managing Opt-In / Obtaining Consent**

GDPR doesn’t change when Data Controllers need consent, it changes how to get consent. In those instances where consent is needed for certain marketing activities, consumer consent needs to be active (e.g., no pre-checked boxes or silence as assent), unbundled, and offers of services may not be made conditional upon the Data Subject giving consent. There may even be instances where certain consents need to be refreshed to be able to continue using data going forward.

As your data processor, Adobe is not able to provide legal advice on obtaining consent. Consult your legal team for guidance. We recommend that you work with a consent management solution providers such as [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) or [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/) to provide better recommendations on this. Adobe has partnered with several such providers to assist with this integration via Adobe Launch.

Audience Manager customers could store user consent for various use cases such as advertising or personalization as traits in Audience Manager. Building segments with these traits will then include only users providing the respective consent for each of these use cases. Please note that using this approach does not stop data collection but will only impact data usage when you send segments for activation. When users withdraw their consent, you can remove these traits from user profile using the Audience Manager [inbound batch process](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) or Audience Manager opt-out process as detailed below.

<br>&nbsp;

**Managing Opt-Out / Withdrawal of Consent**

Opt out can be managed for the Adobe Experience Cloud via the [Your Privacy Choices](https://www.adobe.com/privacy/opt-out.html#customeruse) page. 1-click features let your end users control and opt out of data collection by the Adobe Experience Cloud advertising solutions (including Audience Manager). Specifically, see the [business customer section](https://www.adobe.com/privacy/opt-out.html#customeruse) of the Privacy Choices page. For Browsers that do not support third-party cookies, see [Declared ID targeting](../../features/declared-ids.md#declared-id-targeting). For mobile devices, please retrieve the relevant Audience Manager identifiers and call the Audience Manager opt-out APIs as mentioned in the [Declared ID Opt-Out examples](../../features/declared-ids.md#opt-out-examples). Following that, you can cease all data collection for those users with the opt out APIs from Mobile SDK - see [Android devices](https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html) and [iOS devices](https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html). You can find additional details for opt-out in the [Audience Manager Opt-Out Documentation](../../overview/data-security-and-privacy/opt-out-management.md).

<br>&nbsp;

**Submitting Audience Manager GDPR Access and Delete Requests to Adobe**

You can submit Individual GDPR requests for Access and Delete either through the [GDPR Client Services UI](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) or by calling the [GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-id-onboarding.md). Any [Audience Manager identifiers](../data-security-and-privacy/privacy-regulations-compliance.md#aam-ids), can be submitted in the requests along with their respective namespace IDs (data source IDs). If you submit cross device identifiers such as CRM IDs, Audience Manager will take action on the authenticated profile as well as the device ids linked to it. It is recommended that customers use the Audience Manager Unique User ID (AAM UUID) whenever possible.

<br>&nbsp;

**Managing Access Requests**

Before May 25th, 2018, Audience Manager supported accessing traits, Customer IDs and segments associated with a unique ID within Audience Manager, manually. As of May 25, 2018, we support these requests in the manner described above with various product and services enhancements. In addition to traits, Customer IDs, segments, a response to Access request includes a summary of total number of traits and segments, trait type, descriptions of traits and segments along with the respective data source names. The Access response also includes second party and third-party data accessible to the Data Controller along with the first party data. See more in [Data Access Requests](../data-security-and-privacy/privacy-regulations-compliance.md#access-data).

<br>&nbsp;

**Managing Requests for Deletion**

Before May 25th, 2018, Audience Manager supported the manual deletion of traits, Customer IDs and segments associated with a unique ID within Audience Manager. Upon GDPR coming into effect, we support these requests in the manner described above with various product and service enhancements. In addition to the delete operation, the respective Audience Manager identifiers for the Data Subject will be opted out of further data collection and the respective ID mappings will be removed. See more in [Data Deletion Requests](../data-security-and-privacy/privacy-regulations-compliance.md#delete-data).

<br>&nbsp;

**Second Party Data Providers & Managing Consent**

Second Party Data Providers are generally also Data Controllers and own the process for obtaining any needed consent from the Data Subject to share data with their second party data partners. It is the responsibility of the Audience Manager Customer to determine if the Second Party Data Provider has obtained the necessary consent for your use case. More details on obtaining consent is covered above.

<br>&nbsp;

**Third Party Data Providers & Managing Consent**

Data Providers are also Data Controllers and own their process for obtaining consent and managing access/delete/correction requests. Adobe is proactively requesting that Data Providers update their company profile information within [Adobe Audience Finder](https://www.adobe-audience-finder.com/) with additional information on user data collection. Information will be sourced from the Data Providers and the goal is to have the tool updated by Q2 2018. However, it is up to each Audience Manager Customer to determine that the Third Party Data Provider has obtained the necessary consent for that customer’s use case. Adobe makes no representations about the scope or validity of the consent obtained or reported by a Third Party Data Provider for a given use case.

<br>&nbsp;

**Impact of Delete Requests for Audience Activation**

Audience Manager notifies activation partners about deletion requests by sending them unsegment information for Data Subjects requesting deletion of certain data. However, some activation partners: 1) cannot support unsegment (or remove segment) requests from Adobe and/or 2) are not able to receive updates from us with a frequency of less than 30 days. In those cases, Audience Manager Customers are not able to send delete requests to activation partners in an automated way through Audience Manager. The [GDPR Partner Unsegment documentation](aam-gdpr-partners.md) provides information about unsegment capabilities and frequency of data exchange for all activation partners.

<br>&nbsp;

**Data Retention in Audience Manager**

Applying appropriate, secure, and timely data retention policies to your data is an important part of complying with GDPR. Audience Manager Customers have the ability to set custom retention periods on traits and segments by defining the required TTL (time to live). We have reduced the retention period for [!UICONTROL Customer Data Feeds] ( [!UICONTROL CDF]) and [!UICONTROL Batch Outbound] orders to 8 days. We will also be applying a retention period for inactive CRM profiles and ID mappings. Please find the more details about retention periods in our [Data Retention FAQ](../../faq/faq-privacy.md).

<br>&nbsp;

**Managing Requests for Data Correction**

Given that Audience Manager is not the source of the data, there is a limited role for data correction in Audience Manager. The correction could mean that the Data Subject has requested to either be disqualified from an incorrect trait/segment or qualified to the desired trait/segment. Audience Manager Customers can choose to capture the relevant signals/traits/segments against user profiles and send this information through offline data ingestion to Audience Manager. Please note that the user will continue to get qualified to the original trait and segments if they repeat their behavior.

<br>&nbsp;

**Cross-Border Data Transfers**

GDPR doesn’t prohibit transfer of data outside of Europe. It requires that the privacy protections on European data persist wherever the data is transferred. Visit the [Adobe Privacy Center](https://www.adobe.com/privacy/eudatatransfers.html) to learn more.

<br>&nbsp;

## GDPR Readiness Guidance for Audience Manager Customers (Data Controllers) {#gdpr-readiness-guidance}

We recommend being proactive in the areas of data governance and organizational readiness. This ensures that your consumer data will be organized for processes related to access or delete requests, your teams will be enabled and empowered to manage these requests, and your consumers (Data Subjects) will have a positive, differentiated experience with your brand.

Please note, as your Data Processor, Adobe cannot provide legal advice on GDPR requirements and the process for obtaining consent from your Data Subjects. Please consult with your legal counsel for guidance on GDPR compliance for your organization.

<br>&nbsp;

**Data Governance: Start thinking about how your consumer data is managed in your in Audience Manager instance**

* Review the various customer IDs your marketing teams use to identify users in Audience Manager, along with the data sources in which they are stored. This will streamline the process for requests (such as delete or access) since certain data types will be hashed by your teams prior to ingestion in Audience Manager. 
* IDFA/GAID mobile device IDs are used for multiple use cases in Audience Manager. If you are using Adobe Mobile SDK, please make sure to submit the Experience Cloud ID (MID) along with IDFA/GAID to make sure the GDPR responses are complete. 
* With the definition of personal data becoming more expansive, IP addresses may be considered personal data in your region. Proactively engage with Adobe Consulting to obfuscate the last octet. 
* Determine a validation/authentication policy & process for confirming the identity of a Data Subject when they make a GDPR request. 
* Consider using [Data Export Controls](../../features/data-export-controls.md) to block audience activation to technologies that house personal data. For example, segments with third-party data should not syndicated to email service providers. Set a [!UICONTROL Data Export Control] to ensure that no one in your organization can accidentally activate this data. 
* Begin utilizing [Role Based Access Controls](../../features/administration/administration-overview.md) to ensure the right teams have access to intended data. 
* Consider appropriate [retention periods](../../faq/faq-privacy.md#data-retention-faq) for the data. 
* Review identity linkage and privacy policies and legal requirements to see when and where it is appropriate to tie identity sets together; use appropriately via Audience Manager’s [Profile Merge Rules](../../features/profile-merge-rules/merge-rules-overview.md).

<br>&nbsp;

**Organizational Readiness: Establish a business process**

* Identify a process to receive/respond to Data Subject requests. Consider building an automated tool to submit requests to Audience Manager. 
* Appoint a privacy point of contact within your DMP center of excellence. Connect your organization’s privacy point of contact with your Audience Manager product usage team to understand how you might manage your input ID requirements. 
* Conduct a data review prior to sharing with the Data Subject. Document the steps you put in place, to help you establish accountability.

