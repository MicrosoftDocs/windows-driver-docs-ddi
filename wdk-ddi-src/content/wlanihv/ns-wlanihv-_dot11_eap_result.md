---
UID: NS:wlanihv._DOT11_EAP_RESULT
title: _DOT11_EAP_RESULT
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_eap_result.htm
old-project: netvista
ms.assetid: 90898f5c-ffc1-4e6c-a8f8-ba839f449082
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_EAP_RESULT, DOT11_EAP_RESULT, *PDOT11_EAP_RESULT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wlanihv.h
req.include-header: Winlanihv.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_EAP_RESULT
req.alt-loc: wlanihv.h
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
req.typenames: DOT11_EAP_RESULT, *PDOT11_EAP_RESULT
req.product: Windows 10 or later.
---

# _DOT11_EAP_RESULT structure



## -description

## -syntax

````
typedef struct _DOT11_EAP_RESULT {
  UINT32         dwFailureReasonCode;
  EAP_ATTRIBUTES *pAttribArray;
} DOT11_EAP_RESULT, *PDOT11_EAP_RESULT;
````


## -struct-fields

### -field dwFailureReasonCode

The reason code returned by the EAP method. The meaning of the code is specific to the EAP
     method.


### -field pAttribArray

A pointer to an EAP_ATTRIBUTES array structure that contains the EAP attributes returned by the
     authentication session. For more information about EAP_ATTRIBUTES, see the Microsoft Windows SDK
     documentation.


## -remarks
