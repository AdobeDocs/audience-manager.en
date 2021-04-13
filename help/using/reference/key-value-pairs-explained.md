---
description: Defines and describes standard and serialized key-value pairs.
keywords: integration code
seo-description: Defines and describes standard and serialized key-value pairs.
seo-title: Key-Value Pairs Explained
solution: Audience Manager
title: Key-Value Pairs Explained
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: Reference
exl-id: de4e6fdb-2d6d-4fed-9255-9438b42b2570
---
# Key-Value Pairs Explained{#key-value-pairs-explained}

Defines and describes standard and serialized key-value pairs.

<!-- 

c_key_value_explained.xml

 -->

A key-value pair consists of two related data elements: A key, which is a constant that defines the data set (e.g., gender, color, price), and a value, which is a variable that belongs to the set (e.g., male/female, green, 100). Fully formed, a key-value pair could look like these:

* `gender = male` 
* `color = green` 
* `price > 100`

## Standard and Serialized Key-Value Pairs {#standard-serialized-pairs}

Destinations accept key-value data in *`standard`* or *`serialized`* format. Standard formatting organizes data into separate key-value pairs. Each key is stated explicitly, even when used again to define a different value. By contrast, serialized formatting condenses multiple values into one set defined by a single key. Also, in a serialized pair, a special indicator is used to separate the values within the key-value set. Finally, standard and serialized key-values can contain single or multiple values. The following table provides examples of standard and serial key-value formats.  

|  Formatting  | Single Key  | Key-Value Pairs  |
|---|---|---|
|  **Standard** | `x=1&x=2`  | `x=1&x=2&y=3&y=4`  |
|  **Serialized** | `x=1;2`  | `x=1;2&y=3;4`  |



## Keys, Delimiters, and Separators {#keys-delimiters-separators}

When working with serialized data, you must specify the characters that separate values *within* and *between* the key-value pairs. Elements in key-value pairs are defined as follows:

* **Key:** A unique identifier in the key-value pair. 
* **Value delimiter:** Separates individual key-value pairs. 
* **Key-value separator:** Separates a key from the values within a key-value pair. 
* **Serial separator:** Separates individual values within serialized key-value pairs.

## Standard and Serialized Key-Value Elements {#standard-serialized-key-value-elements}


Type | Example | Key | Key-Value Separator | Key-Value Delimiter | Serial Separator
---------|----------|---------|---------|----------|---------
 **Single key** (standard) | `x=1&x=2` | `x` | `=` | `&` | n/a
 **Key-value pairs** (standard) | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | n/a
 **Single key** (serial) | `x=1;2;3` | `x` | `=` | n/a | `;`
 **Key-value pairs** (serial) | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;`
