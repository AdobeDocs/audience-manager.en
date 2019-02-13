---
description: Recommendations and use cases for prospecting, retargeting, and personalization for unknown users with an external device graph. An external device graph is defined as a device graph that is separate from Audience Manager. This includes the Adobe Experience Cloud Device Co-op and other integrations Adobe has with third-party deterministic or probabilistic device graph companies.
seo-description: Recommendations and use cases for prospecting, retargeting, and personalization for unknown users with an external device graph. An external device graph is defined as a device graph that is separate from Audience Manager. This includes the Adobe Experience Cloud Device Co-op and other integrations Adobe has with third-party deterministic or probabilistic device graph companies.
seo-title: External Device Graph Use Cases
solution: Audience Manager
title: External Device Graph Use Cases
uuid: f4bc822d-39d2-4680-90ed-7ee2ead6db6f
---

# External Device Graph Use Cases {#external-device-graph-use-cases}

Recommendations and use cases for prospecting, retargeting, and personalization for unknown users with an external device graph. An external device graph is defined as a device graph that is separate from Audience Manager. This includes the [!DNL Adobe Experience Cloud Device Co-op] and other integrations Adobe has with third-party deterministic or probabilistic device graph companies.

## Recommendations {#section_7C93DAA7927A4203B9617A560CCC1F02}

Consider the [!DNL Experience Cloud Device Co-op] and third-party device graph options for campaigns that:

* Have a low level of authentication across their digital properties. Use the [Profile Link device graph option](../../features/profile-merge-rules/merge-rule-definitions.md#section_E83D68EC2ADA4030B1D0206AE6A6E8BF) if you have a large number of authenticated users.
* Target large audiences. The [!DNL Experience Cloud Device Co-op] and third-party device graphs contain authenticated and un-authenticated data.
* Segment authenticated and/or unauthenticated visitors at the individual and household level.

![](assets/merge-rule-triangle1.png)

## Prospecting/Branding Use Case {#section_B6877E4AFC194EBDA6153A4719E224E8}

A branding campaign is designed to reach as many people as possible. It places few limits on segment qualification. But, these campaigns can waste budget and impressions by constantly targeting people who see your content multiple times and don't convert. A [!UICONTROL Profile Merge] rule that uses the [!DNL Device Co-op] or third-party option can help you create an efficient branding campaign. For example, you can add these unknown users to a "not in-market" segment after seeing them across multiple devices for your set frequency cap.

<table id="table_00F6EED172574E80A38CADA8A92A23B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2">This use case assumes these conditions: <p> 
     <ul id="ul_F5CA7EE525774F7EBA5FBB5F94E4EDC8"> 
      <li id="li_81AE304924724146A24FAB5B6533AD8E">You want to deliver a maximum of 10 impressions to an anonymous user for a specific ad campaign. </li> 
      <li id="li_E371F989735245B0B82433DE240D56D0">A user has multiple devices and may or may not have authenticated to your site. </li> 
      <li id="li_9231ABE15CA249E6B79D8BF0E511FD33">An anonymous user sees the ad a total of 10 times while browsing in an unauthenticated state on their current device and up to 3 devices linked by an external device graph. </li> 
      <li id="li_8C276C07019C49EFA3A0D0D54CF73C31">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify anonymous users after they have seen 10 impressions. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Results</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_8E988B1005324526BC6DC6637BBACCFB"> 
      <li id="li_C9DD546754914BACB8F4C92C7D4ED70E">Merges the anonymous, unauthenticated activity collected from the current device and the 3 devices linked by the external device graph (the ad impressions from each device). </li> 
      <li id="li_FB55CB9116074525BA30FF062D1136AE">Evaluates the unauthenticated user for segment qualification based on a combination of anonymous activity across all 3 devices linked by the external device graph and the current device. </li> 
      <li id="li_B28EB32F718145A7ABBDAC0AF75E2AFC">Sends the segment to any real-time destination for use as a suppression segment on the current device and all 3 devices linked by the external device graph. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Retargeting or Site Personalization Use Case {#section_DDA1F5FC497E47B0BFBF199BA92474F5}

These strategies are designed to bring an unauthenticated or unknown user back to your site or personalize their browsing experience while they're on-site.

<table id="table_0EE2052AA3E744B3B76036FC06B5A453"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2">This use case assumes these conditions: <p> 
     <ul id="ul_FD0B869B4AF3453FAEC9BA3A45ABF039"> 
      <li id="li_8E30BAED42E94AB3B81FCB1C7464E5FC">You want to deliver a personalized on-site and/or off-site experience to an anonymous user based on their activity on your site while in an unauthenticated state. </li> 
      <li id="li_3DBE53BA94324F1BA1C52A37AD4E426C">A user has multiple devices and may or may not have authenticated to your site. </li> 
      <li id="li_F867AFBDC1A54CD6A68AB0EC196E27C9">A user views multiple pages on your site while browsing in an unauthenticated state on their current device and up to 3 devices linked by an external device graph. </li> 
      <li id="li_7E35D77949CE4E69BD51655AA4C40BEE">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify users after they have viewed multiple pages on your site while browsing in an unauthenticated state. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Results</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="wintitle"> Audience Manager</span>: </p> <p> 
     <ul id="ul_301339426B0643B295DC5B17E1939CFB"> 
      <li id="li_7E8BC3B179804F4A929497DE81E76911">Merges the anonymous, unauthenticated activity collected from the current devices and the 3 devices linked by the external device graph (the multiple page views from each device). </li> 
      <li id="li_803EFD58AA124A5BBC8279C4DC695544">Evaluates the unauthenticated user for segment qualification based on a combination of anonymous activity across all 3 devices linked by the external device graph and the current device. </li> 
      <li id="li_98D749268CC5456CBC9CF3BF5EB91BA8">Sends the segment to any real-time destination to deliver a personalized on-site and/or off-site experience across the current device and all 3 devices linked by the external device graph. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Profile Merge Rule] Options for [!UICONTROL External Device Graph] Use Cases {#section_48CFAB21B82A4C88B0FA2CC69187E2DF}

Your merge rule options for these use cases would look similar to the available options shown below. The [!UICONTROL Authenticated Profile] options are deactivated because these settings are only available when you select **[!UICONTROL Current Authenticated Profile]** or **[!UICONTROL Last Authenticated Profile]**. Your [!UICONTROL Device Options] will vary depending on the type of device graph setting that you want to use or that is available to you.

![](assets/merge-rules-external.png)

For more information about how these device graph processes work, download our PDF, [Audience Manager and External Device Graphs](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf).

>[!MORE_LIKE_THIS]
>
>* [Profile Link Device Graph Use Cases](../../features/profile-merge-rules/profile-link-use-case.md#concept_5D9D32E18BB94F318A8BA0229335F1B9)
>* [General Use Cases for Profile Merge Rules](../../features/profile-merge-rules/merge-rule-targeting-options.md#concept_7F8EC9D100AE442185B2C3EE65814DD2)
>* [Profile Merge Rules FAQ](../../faq/faq-profile-merge.md#concept_C8E29A974E194B62B0BAC1CCDD0DF4FF)
