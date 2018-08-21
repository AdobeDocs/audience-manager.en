---
description: Send information about search engine type and keyword searches to Audience Manager.
seo-description: Send information about search engine type and keyword searches to Audience Manager.
seo-title: Capture Search Engine Types and Keyword Search Terms
solution: Audience Manager
title: Capture Search Engine Types and Keyword Search Terms
uuid: 71c45159-06b7-4de5-afa1-a25541f2fe16
index: y
internal: n
snippet: y
translate: y
---

# Capture Search Engine Types and Keyword Search Terms

**Supported Search Engines** 

By default, ` DIL.getSearchReferrer` recognizes searches from these search engines (including international variations): 
* AOL
* Ask
* Bing
* Google
* Yahoo!


**Description** 

The following code demonstrates how to get the search referrer for any of the supported search engines. In this case, let's assume a user searched on the term "homes" from Google Canada ( ` www.google.ca`). This code will help you capture those search terms and send them to Audience Manager. 

**Basic Code** 

Basic code for getting the search referrer (from google.com, for example) looks like this: 
```
javavar search_referrer = DIL.tools.getSearchReferrer();
```


**Listed Search Engine Code Sample** 

In this case, let's assume that a user searched for the term "homes" from Google Canada (www.google.ca). Note how the code prefixes the required ` c_` parameter to search engine ( ` c_se`) and search term ( ` c_st`). ` c_` is a [ required prefix ](../../../c_features/c_tb_overview/c_tb_reference/r_tb_variable_prefixes.md#reference_E6F1E4257F664FC2A797C406BF147ABC) that identifies these as customer-defined variables to Audience Manager. 
```
javavar adobe_dil = DIL.create({partner:" 
<i>partner name</i>"}); 
var se = DIL.tools.getSearchReferrer(); 
 
if (se && se.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
```


**Unlisted Search Engine Code Sample** 

In this case, let's assume that a user searched for the term "homes" from ` dogpile.com`. Because Dogpile is not supported by default, you can configure DIL to recognize this search engine and return the search terms to Audience Manager. Your code could look similar to the following: 
```
javavar adobe_dil = DIL.create({partner:" 
<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, {  
    hostPattern:/dogpile\./, 
    queryParam:"q" 
}); 
 
if (se && se.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
```

