---
UID: NS:nfcsedev._SECURE_ELEMENT_ENDPOINT_LIST
title: "_SECURE_ELEMENT_ENDPOINT_LIST"
author: windows-driver-content
description: The output parameter for IOCTL_NFCSE_ENUM_ENDPOINTS.
old-location: nfpdrivers\_secure_element_endpoint_list.htm
old-project: nfpdrivers
ms.assetid: 0F69EE38-C124-47A6-B3CA-31F089657894
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: nfcsedev/_SECURE_ELEMENT_ENDPOINT_LIST, PSECURE_ELEMENT_ENDPOINT_LIST, P_SECURE_ELEMENT_ENDPOINT_LIST, P_SECURE_ELEMENT_ENDPOINT_LIST structure pointer [Near-Field Proximity Drivers], *PSECURE_ELEMENT_ENDPOINT_LIST, SECURE_ELEMENT_ENDPOINT_LIST, nfpdrivers._secure_element_endpoint_list, SECURE_ELEMENT_ENDPOINT_LIST structure [Near-Field Proximity Drivers], nfcsedev/P_SECURE_ELEMENT_ENDPOINT_LIST, _SECURE_ELEMENT_ENDPOINT_LIST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: nfcsedev.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	nfcsedev.h
apiname:
-	SECURE_ELEMENT_ENDPOINT_LIST
product: Windows
targetos: Windows
req.typenames: SECURE_ELEMENT_ENDPOINT_LIST, *PSECURE_ELEMENT_ENDPOINT_LIST
---

# _SECURE_ELEMENT_ENDPOINT_LIST structure


## -description


The output parameter for <a href="..\nfcsedev\ni-nfcsedev-ioctl_nfcse_enum_endpoints.md">IOCTL_NFCSE_ENUM_ENDPOINTS</a>.


## -syntax


````
typedef struct _SECURE_ELEMENT_ENDPOINT_LIST {
  DWORD                                                            NumberOfEndpoints;
  _Field_size_(NumberOfEndpoints)
    SECURE_ELEMENT_ENDPOINT_INFO EndpointList[ANYSIZE_ARRAY];
} SECURE_ELEMENT_ENDPOINT_LIST, *P_SECURE_ELEMENT_ENDPOINT_LIST;
````


## -struct-fields




#### - NumberOfEndpoints

The number of enumerated endpoints on the NFC controller.


### -field EndpointList

 



#### - EndpointList[ANYSIZE_ARRAY]

An array of <a href="..\nfcsedev\ns-nfcsedev-_secure_element_endpoint_info.md">SECURE_ELEMENT_ENDPOINT_INFO</a> structures.

