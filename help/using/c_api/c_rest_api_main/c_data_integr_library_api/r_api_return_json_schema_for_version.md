---
description: A GET method that returns the JSON schema for the version. Supports using alias LATEST for version to get the latest version of DIL.
seo-description: A GET method that returns the JSON schema for the version. Supports using alias LATEST for version to get the latest version of DIL.
seo-title: Return JSON Schema for Version
solution: Audience Manager
title: Return JSON Schema for Version
uuid: 761d1ab0-2915-4581-95b8-30083e002668
index: y
internal: n
snippet: y
translate: y
---

# Return JSON Schema for Version


>**Request** 

>` GET https://api.demdex.com/v1/dil/<version>` 

>**Sample Response** 

>A successful request returns response code ` ["4.0", "4.1"]` and data as shown below. 
>
>```
>{ 
>    "type": "object", 
>    "$schema": "http://json-schema.org/draft-03/schema", 
>    "required": true, 
>    "additionalProperties": false, 
>    "properties": { 
>        "core": { 
>            "id": "core", 
>            "required": true, 
>            "type": "object", 
>            "properties": { 
>                "code": { 
>                    "type": "boolean", 
>                    "required": true, 
>                    "id": "code" 
>                }, 
>                "instanceVariable": { 
>                    "type": "string", 
>                    "id": "instanceVariable", 
>                    "required": false 
>                }, 
>                "create": { 
>                    "type": "object", 
>                    "id": "create", 
>                    "required": false, 
>                    "properties": { 
>                        "initConfig": { 
>                            "additionalProperties": false, 
>                            "type": "object", 
>                            "id": "initConfig", 
>                            "required": true, 
>                            "properties": { 
>                                "declaredId": { 
>                                    "id": "declaredId", 
>                                    "required": false, 
>                                    "type": "object", 
>                                    "additionalProperties": false, 
>                                    "properties": { 
>                                        "dpid": { 
>                                            "id": "dpid", 
>                                            "required": true, 
>                                            "type": "string" 
>                                        }, 
>                                        "dpuuid": { 
>                                            "id": "dpuuid", 
>                                            "required": true, 
>                                            "type": "string" 
>                                        } 
>                                    } 
>                                }, 
>                                "containerNSID": { 
>                                    "type": "number", 
>                                    "id": "containerNSID", 
>                                    "required": false 
>                                }, 
>                                "disableDestinationPublishingIframe": { 
>                                    "type": "boolean", 
>                                    "id": "disableDestinationPublishingIframe", 
>                                    "required": false 
>                                }, 
>                                "enableErrorReporting": { 
>                                    "type": "boolean", 
>                                    "id": "enableErrorReporting", 
>                                    "required": false 
>                                }, 
>                                "iframeAkamaiHTTPS": { 
>                                    "type": "boolean", 
>                                    "id": "iframeAkamaiHTTPS", 
>                                    "required": false 
>                                }, 
>                                "iframeAttachmentDelay": { 
>                                    "type": "number", 
>                                    "id": "iframeAttachmentDelay", 
>                                    "required": false 
>                                }, 
>                                "mappings": { 
>                                    "type": "object", 
>                                    "id": "mappings", 
>                                    "required": false, 
>                                    "additionalProperties": { 
>                                        "type": "string" 
>                                    } 
>                                }, 
>                                "removeFinishedScriptsAndCallbacks": { 
>                                    "type": "boolean", 
>                                    "id": "removeFinishedScriptsAndCallbacks", 
>                                    "required": false 
>                                }, 
>                                "uuidCookie": { 
>                                    "type": "object", 
>                                    "id": "uuidCookie", 
>                                    "additionalProperties": false, 
>                                    "required": false, 
>                                    "properties": { 
>                                        "days": { 
>                                            "type": "number", 
>                                            "id": "days", 
>                                            "required": false 
>                                        }, 
>                                        "domain": { 
>                                            "type": "string", 
>                                            "id": "domain", 
>                                            "required": false 
>                                        }, 
>                                        "name": { 
>                                            "type": "string", 
>                                            "id": "name", 
>                                            "required": true 
>                                        }, 
>                                        "path": { 
>                                            "type": "string", 
>                                            "id": "path", 
>                                            "required": false 
>                                        }, 
>                                        "secure": { 
>                                            "type": "boolean", 
>                                            "id": "secure", 
>                                            "required": false 
>                                        } 
>                                    } 
>                                }, 
>                                "visitorService": { 
>                                    "type": "object", 
>                                    "id": "visitorService", 
>                                    "required": false, 
>                                    "properties": { 
>                                        "namespace": { 
>                                            "type": "string", 
>                                            "id": "namespace", 
>                                            "required": true 
>                                        } 
>                                    } 
>                                } 
>                            } 
>                        } 
>                    } 
>                } 
>            } 
>        }, 
>        "options": { 
>            "id": "options", 
>            "type": "object", 
>            "required": false, 
>            "properties": { 
>                "minify": { 
>                    "id": "minify", 
>                    "required": false, 
>                    "type": "boolean" 
>                } 
>            } 
>        }, 
>        "include": { 
>            "type": "object", 
>            "id": "include", 
>            "required": false, 
>            "properties": { 
>                "modules": { 
>                    "type": "object", 
>                    "id": "modules", 
>                    "required": false, 
>                    "additionalProperties": false, 
>                    "properties": { 
>                        "GoogleAnalytics": { 
>                            "type": "object", 
>                            "id": "GoogleAnalytics", 
>                            "required": false, 
>                            "properties": { 
>                                "code": { 
>                                    "id": "code", 
>                                    "type": "boolean", 
>                                    "required": true 
>                                } 
>                            } 
>                        }, 
>                        "Peer39": { 
>                            "type": "object", 
>                            "id": "Peer39", 
>                            "required": false, 
>                            "properties": { 
>                                "code": { 
>                                    "id": "code", 
>                                    "type": "boolean", 
>                                    "required": true 
>                                } 
>                            } 
>                        }, 
>                        "SiteCatalyst": { 
>                            "type": "object", 
>                            "id": "SiteCatalyst", 
>                            "required": false, 
>                            "additionalProperties": false, 
>                            "properties": { 
>                                "code": { 
>                                    "type": "boolean", 
>                                    "id": "code", 
>                                    "required": true 
>                                }, 
>                                "init": { 
>                                    "type": "object", 
>                                    "id": "init", 
>                                    "required": false, 
>                                    "additionalProperties": false, 
>                                    "properties": { 
>                                        "siteCatalystInstance": { 
>                                            "type": "string", 
>                                            "id": "siteCatalystInstance", 
>                                            "required": true 
>                                        }, 
>                                        "dilInstance": { 
>                                            "type": "string", 
>                                            "id": "dilInstance", 
>                                            "required": true 
>                                        }, 
>                                        "trackedVariables": { 
>                                            "id": "trackedVariables", 
>                                            "required": false, 
>                                            "type": "object", 
>                                            "properties": { 
>                                                "iteratedNames": { 
>                                                    "type": "array", 
>                                                    "id": "iteratedNames", 
>                                                    "required": false, 
>                                                    "items": { 
>                                                        "type": "object", 
>                                                        "id": "0", 
>                                                        "required": true, 
>                                                        "properties": { 
>                                                            "maxIndex": { 
>                                                                "type": "number", 
>                                                                "id": "maxIndex", 
>                                                                "required": true 
>                                                            }, 
>                                                            "name": { 
>                                                                "type": "string", 
>                                                                "id": "name", 
>                                                                "required": true 
>                                                            } 
>                                                        } 
>                                                    } 
>                                                }, 
>                                                "names": { 
>                                                    "type": "array", 
>                                                    "additionalItems": false, 
>                                                    "id": "names", 
>                                                    "required": false, 
>                                                    "items": [ 
>                                                        { 
>                                                            "type": "string", 
>                                                            "required": true 
>                                                        }, 
>                                                        { 
>                                                            "type": "string", 
>                                                            "required": false 
>                                                        }, 
>                                                        { 
>                                                            "type": "string", 
>                                                            "required": false 
>                                                        }, 
>                                                        { 
>                                                            "type": "string", 
>                                                            "required": false 
>                                                        }, 
>                                                        { 
>                                                            "type": "string", 
>                                                            "required": false 
>                                                        }, 
>                                                        { 
>                                                            "type": "string", 
>                                                            "required": false 
>                                                        }, 
>                                                        { 
>                                                            "type": "string", 
>                                                            "required": false 
>                                                        }, 
>                                                        { 
>                                                            "type": "string", 
>                                                            "required": false 
>                                                        }, 
>                                                        { 
>                                                            "type": "string", 
>                                                            "required": false 
>                                                        } 
>                                                    ] 
>                                                } 
>                                            } 
>                                        } 
>                                    } 
>                                } 
>                            } 
>                        } 
>                    } 
>                }, 
>                "tools": { 
>                    "type": "object", 
>                    "id": "tools", 
>                    "required": false, 
>                    "additionalProperties": false, 
>                    "properties": { 
>                        "getMetaTags": { 
>                            "type": "boolean", 
>                            "id": "getMetaTags", 
>                            "required": false 
>                        }, 
>                        "getSearchReferrer": { 
>                            "type": "boolean", 
>                            "id": "getSearchReferrer", 
>                            "required": false 
>                        }, 
>                        "decomposeURI": { 
>                            "type": "boolean", 
>                            "id": "decomposeURI", 
>                            "required": false 
>                        } 
>                    } 
>                } 
>            } 
>        } 
>    } 
>} 
>
>```
