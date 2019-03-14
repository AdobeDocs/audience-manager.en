---
description: Segment Builder lets you build trait rules for a segment using a code editor. Click the Segment Expressions (Code View) tab in the Traits panel to access this feature.
seo-description: Segment Builder lets you build trait rules for a segment using a code editor. Click the Segment Expressions (Code View) tab in the Traits panel to access this feature.
seo-title: Code Syntax Used in the Segment Expression Editor
solution: Audience Manager
title: Code Syntax Used in the Segment Expression Editor
uuid: 7b4b06ca-7879-4501-8ba7-b2b6467b8a3b
---

# Code Syntax Used in the [!UICONTROL Segment Expression Editor] {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] lets you build trait rules for a segment using a code editor. Click the **[!UICONTROL Segment Expressions (Code View)]** tab in the [!UICONTROL Traits] panel to access this feature.

## [!UICONTROL Expression Builder] Code Syntax

You can add trait rules to a segment with code instead of using drag and drop features. When coding, replace italicized elements in the example with an actual expression or value. The base code uses following syntax:

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>By default, [!DNL Boolean] [!UICONTROL OR] conditions apply to multiple traits *within* an expression.

### Join Segments with [!DNL Boolean] Operators

To build groups of segments, wrap the frequency function in parenthesis and set the relationship *between* each expression with a [!DNL Boolean] operator ([!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT]).

### Parameters

>[!NOTE]
>
>All parameters are required unless noted otherwise.

|  Name or Variable  | Description  |
|---|---|
|  `FREQUENCY`  | A literal that must precede the expression.  |
|  ` [`&lt;`traitID`&gt;`T]`  | An array of trait IDs followed by the letter `T`. Separate multiple traits with a comma. For example, `[123T, 456T]`.  |
|  ` <Recency Operator><Numeric Value>D`  | *(Optional)* Sets recency rules on traits in the segment. The letter `D` indicates recency in days.  |
|  ` <Frequency Operator><Numeric Value>`  | Sets frequency rules on traits in the segment.  |

### Allowed Recency and Frequency Operators

Set [recency and frequency](../../features/segments/recency-and-frequency.md#concept_957D9E1977774D28A98ACEE6035E7B37) intervals with a comparison operator and an integer. [!UICONTROL Segment Builder] uses standard expressions like < (less than), > (greater than), == (equal), etc. However, the types of allowed operators vary when you set recency or frequency. The table below lists the allowed recency/frequency operators.  

<table id="table_2F92617CB472442BA5639E24DB4E43D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recency Operators </th> 
   <th colname="col2" class="entry"> Frequency Operators </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_66D11A34097648A997BA5C6CCC38503A"> 
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;= (greater than/equal to) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt;= (less than/equal to) </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;= (greater than/equal to) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt;= (less than/equal to) </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">== (equal to) </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [Recency and Frequency](../../features/segments/recency-and-frequency.md#concept_957D9E1977774D28A98ACEE6035E7B37)
>* [Boolean Expressions in Trait and Segment Builder](../../reference/boolean-expressions-tsb.md#concept_B7537516B5D04CEBB9CFB4F4B780630F)
>* [Working with Comparison Operators in TraitBuilder](../../features/traits/trait-comparison-operators.md#concept_1A1761AA403341D7B91C0E26DC4294F4)
>* [Order of Operations in TraitBuilder Expressions](../../features/traits/trait-operator-precedence.md#concept_F8A8B8B8E4814A86B34493B104D44464)
