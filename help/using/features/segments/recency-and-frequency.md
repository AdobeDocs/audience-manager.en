---
description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-title: Recency and Frequency
solution: Audience Manager
title: Recency and Frequency
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
---

# Recency and Frequency {#recency-and-frequency}

In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.

Audience Manager defines [!DNL recency] and [!DNL frequency] as follows:

* **Recency:** The number of days during which a user viewed or qualified for one (or more) traits.
* **Frequency:** The rate at which a user viewed or qualified for one (or more) traits.

Recency and frequency settings help you segment visitors based on their real (or perceived) level of interest in a site, section, or particular creative. For example, users who qualify for a segment with high recency/frequency requirements may be more interested in a site or product than users who visit less often or less frequently.

## Location of Recency and Frequency Settings {#section_49C03FF5D0554A7EB40AC42D46E17E09}

In [!UICONTROL Segment Builder], recency and frequency settings are located in the [!UICONTROL Basic View] section of the [!UICONTROL Traits] panel. Click the clock icon to expose these controls.

![](assets/recency_frequency.png)

## Limitations and Rules {#section_19CA9E5DEAE7455EB512D541B9B612DE}

Review and understand these limits and rules when you want to apply recency and frequency to traits in your segments.

### Recency

<table id="table_026064124C694D75B7A960457D50170B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limit or Rule </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Minimum Value</b> </p> </td> 
   <td colname="col2"> <p>Recency must be greater than 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Third-Party Traits</b> </p> </td> 
   <td colname="col2"> <p>You cannot set recency rules on individual third-party traits or trait groups that contain third-party traits. Recency and frequency applies to your own traits only. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Frequency

<table id="table_EBD621D26C8B4D03933E8C0753C892A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limit or Rule </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Third-Party Traits</b> </p> </td> 
   <td colname="col2"> <p>You cannot set frequency rules on individual third-party traits or trait groups that contain third-party traits. Recency and frequency applies to your own traits only. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Recency Requirements</b> </p> </td> 
   <td colname="col2"> <p>You can configure frequency requirements <i>without</i> configuring recency requirements. Just set a frequency value and leave the recency field blank. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Profile Merge Rules</b> </p> </td> 
   <td colname="col2"> <p>See <a href="../../faq/faq-profile-merge.md#section_05A3000A36AE43A187526241D99EFD85"> Trait Frequency, External Device Graphs, and Profile Merge Rules</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Frequency Capping Examples {#section_61D796D4E5764D49B4FF2DCC52021D2E}

Frequency-capping expressions include all the users whose number of trait realizations is below a desired value. Here are a few examples:

* The expression `frequency([1000T]) <= 5` includes all users that have realized the trait with the ID "1000" a maximum of five times, including users who have not realized the trait.
* When you need recency/frequency requirements to be less than a specific number of times or days, join that trait to another with an `AND` operator. Using the example above, this expression becomes valid when joined with another trait as shown here: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* For advertising frequency-capping use cases, you could create a segment rule similar to this: `(frequency([1000T] <= 2D) >= 5)`. This expression includes all users that have realized the trait with the ID "1000" in the past 2 days at least five times. Set frequency capping by sending this segment to the ad server with a `NOT` set on the segment in the ad server. This approach achieves greater performance in [!DNL Audience Manager] while still serving the same purpose for frequency capping.

>[!MORE_LIKE_THIS]
>
>* [Segment Builder Controls: Traits Section](../../features/segments/segment-builder.md#reference_131791CC12A6431A8AD5F19F4FB48947)
>* [Code Syntax Used in the Segment Expression Editor](../../features/segments/segment-code-syntax.md#reference_22B665FB13BA473EBDD6668A9966AAD9)
