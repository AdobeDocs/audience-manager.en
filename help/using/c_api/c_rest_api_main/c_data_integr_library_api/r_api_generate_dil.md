---
description: A GET method that generates DIL based on passed in request body using the specified version of DIL. If the alias LATEST is used for version in the URL, the latest version of DIL is generated.
seo-description: A GET method that generates DIL based on passed in request body using the specified version of DIL. If the alias LATEST is used for version in the URL, the latest version of DIL is generated.
seo-title: Generate DIL
solution: Audience Manager
title: Generate DIL
uuid: a02635ec-e628-48f9-9840-536f02bc30f4
index: y
internal: n
snippet: y
translate: y
---

# Generate DIL


>**Request** 

>` POST https://api.demdex.com/v1/dil/<version>/generate` 

>**Sample Request** 
>
>```
>{ 
>    core: { 
>        code: true, 
>        instanceVariable: 'dil_instance', 
>        create: { 
>            initConfig: { 
>                declaredId: { 
>                    dpid: '159', 
>                    dpuuid: '456' 
>                }, 
>                containerNSID: 81, 
>                disableDestinationPublishingIframe: false, 
>                enableErrorReporting: false, 
>                iframeAkamaiHTTPS: false, 
>                iframeAttachmentDelay: 575, 
>                mappings: { 
>                    c_k1: 'd_k1', 
>                    c_k2: 'd_k2' 
>                }, 
>                removeFinishedScriptsAndCallbacks: false, 
>                uuidCookie: { 
>                    days: 12, 
>                    domain: 'adobe.com', 
>                    name: 'adobe_did', 
>                    path: '/', 
>                    secure: false 
>                }, 
>                visitorService: { 
>                    namespace: 'demofirst' 
>                } 
>            } 
>        } 
>    }, 
>    options: { 
>        minify: true 
>    }, 
>    include: { 
>        modules: { 
>            GoogleAnalytics: { 
>                code: true 
>            }, 
>            Peer39: { 
>                code: true 
>            }, 
>            SiteCatalyst: { 
>                code: true, 
>                init: { 
>                    siteCatalystInstance: 'sc_instance', 
>                    dilInstance: 'dil_instance', 
>                    trackedVariables: { 
>                        iteratedNames: [{ 
>                            name: 'prop', 
>                            maxIndex: 5 
>                        }, { 
>                            name: 'pev', 
>                            maxIndex: 3 
>                        }], 
>                        names: ['pageName', 'channel', 'campaign', 'products', 'events', 'spe', 'spev1', 'spev2', 'spev3'] 
>                    } 
>                } 
>            } 
>        }, 
>        tools: { 
>            getMetaTags: true, 
>            getSearchReferrer: true, 
>            decomposeURI: true 
>        } 
>    } 
>} 
>
>```
>**Sample Response** 

>A successful update returns response code ` 201 created` along with the DIL JavaScript code. 
