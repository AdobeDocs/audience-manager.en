---
description: Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.
seo-description: Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.
seo-title: Geotargeting With Platform-level Keys
solution: Audience Manager
title: Geotargeting With Platform-level Keys
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
---

# Geotargeting With Platform-level Keys {#geotargeting-with-platform-level-keys}

Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.

<!-- c_tb_platform_vars.xml -->

## Purpose of Platform-level Variables {#section_57C422B2079C480B907279D5B57A6AEF}

Platform-level variables let you take data passed in from a particular site and make it available for targeting across all the properties in your [!DNL Audience Manager] account. These variables are formed by [key-value pairs](../../reference/key-value-pairs-explained.md#concept_E4236E003076483AA939791FE2492B49) with the key prefixed by `d_` as shown below.

## Adding Values to Platform Level Keys {#section_1BAF23A099FF40CEB67DFC330BCB8D53}

For some platform-level keys, you can specify the value yourself. With others, the keys are associated with corresponding [!DNL IP] addresses passed in on an event call. In either case, you still need to specify the value when building traits in [!UICONTROL Trait Builder].

## User Defined Platform-Level Keys {#section_532CE169CFF648BCABEF17A7B0EF1C8C}

You specify the value when building traits with these key-value pairs:  

|  Key  | For Targeting  |
|---|---|
| `d_zx`  |ZIP code (e.g., `d_zx=10022`).  |

## Platform Level Keys Defined by [!DNL IP] Address {#section_C1CCBD2C225F4E898CEE01613899B775}

The values for these keys are determined by matching [!DNL IP] addresses to corresponding geographic and demographic data. However, you'll still have to enter the value parameter when creating the key-value pair in [!UICONTROL Trait Builder].

| Key | For Targeting |
|--- |--- |
|d_area_code|[North America area codes](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes).  For example: <ul><li>**Trait**:  d_area_code=801</li><li>**Trait Name**: Utah</li></ul> |
|d_city|Cities and towns. Download the [cities list](assets/d_city.txt).  For example: <ul><li>Trait:  d_city=bonn</li><li>Trait Name: Bonn</li></ul>  |
|d_country|Values correspond to ISO country codes. For a searchable list of codes, see the [ISO Online Browsing Platform](https://www.iso.org/obp/ui/#home). <br>&nbsp; Targeting for the United Kingdom is the only special case that does not obey ISO 3166. You should use "UK" instead of "GB" for targeting in the United Kingdom.  To target the Netherlands Antilles, the code "AN" has been deprecated since 2010. The area has been dissolved into five separate territorial units. The implication is that for targeting in the Netherlands Antilles, you should not use "AN," but a combination of the country codes for "CW," "SX," and "BQ."  For example:  <br>&nbsp; Trait:  d_country=CZ  <br>&nbsp; Trait Name: Czech Republic <br>&nbsp; Trait:  d_country=UK <br>&nbsp; Trait Name: United Kingdom  <br>&nbsp; Trait:  d_country=CW OR d_country=SX OR d_country=BQ  <br>&nbsp; Trait Name: Netherlands Antilles|
|d_dma_code|Metropolitan area DMA codes. Download the [DMA region list](assets/DMAregions.csv) (.csv format).  For example: <ul><li>Trait:  d_dma_code=807</li><li>Trait Name: San Francisco</li></ul>  |
|d_lat|Latitude (e.g.  d_lat=40.75). Download the [latitudes list](assets/d_lat.txt).|
|d_long|Longitude (e.g.  d_long=73.98). Download the [longitudes list](assets/d_long.txt).|
|d_postal_code|ZIP codes (exclude the extended +4 code). Download the  [postal codes list](assets/d_postal_code.txt).  For example: <ul><li>Trait:  d_postal_code=84004 </li><li>Trait Name: Alpine</li></ul>|
|d_state|2-character abbreviation for a US state. Download the [states codes list](assets/d_state.txt).  For example: <ul><li>Trait:  d_state=NY </li><li>Trait Name: New York</li></ul>d_state contains repeated values for different states in different countries. For example, d_state == "on" matches multiple states: Ontario (in Canada), Ondo (in Nigeria), Oshana (in Namibia). We recommend to couple this signal with others such as d_country for more specific geotargeting.|
|d_region|Regional alphanumeric IDs. Download the [region list](assets/Country_RegionCodes_City.csv).  Then, you can use  this list to match region IDs to region names.|
|d_isp|ISP/organization. Download the [ISP List](assets/d_isp.txt).|

The list of [all location-based signals](assets/all.csv) comprises all the signals above, in the following order: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORE_LIKE_THIS]
>
>* [Prefix Requirements for Key Variables](../../features/traits/trait-variable-prefixes.md#reference_E6F1E4257F664FC2A797C406BF147ABC)
