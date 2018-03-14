---
UID: NS:wwan._WWAN_USSD_EVENT
title: "_WWAN_USSD_EVENT"
author: windows-driver-content
description: The WWAN_USSD_REQUEST structure describes an Unstructured Supplementary Service Data (USSD) event.
old-location: netvista\wwan_ussd_event.htm
old-project: netvista
ms.assetid: 5E90FB65-AF23-47C0-B0E9-2B6EF353D095
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_USSD_EVENT, PWWAN_USSD_EVENT, PWWAN_USSD_EVENT structure pointer [Network Drivers Starting with Windows Vista], WWAN_USSD_EVENT, WWAN_USSD_EVENT structure [Network Drivers Starting with Windows Vista], _WWAN_USSD_EVENT, netvista.wwan_ussd_event, wwan/PWWAN_USSD_EVENT, wwan/WWAN_USSD_EVENT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_USSD_EVENT
product: Windows
targetos: Windows
req.typenames: WWAN_USSD_EVENT, *PWWAN_USSD_EVENT
req.product: Windows 10 or later.
---

# _WWAN_USSD_EVENT structure


## -description


The WWAN_USSD_REQUEST structure describes an Unstructured Supplementary Service Data (USSD) event.


## -syntax


````
typedef struct _WWAN_USSD_EVENT {
  WWAN_USSD_EVENT_TYPE    EventType;
  WWAN_USSD_SESSION_STATE SessionState;
  WWAN_USSD_STRING        UssdString;
} WWAN_USSD_EVENT, *PWWAN_USSD_EVENT;
````


## -struct-fields




### -field EventType

The type of USSD event.


### -field SessionState

The USSD string is the first message of a USSD session.


### -field UssdString

The USSD string that accompanies the event.


## -see-also

<a href="..\wwan\ne-wwan-_wwan_ussd_event_type.md">WWAN_USSD_EVENT_TYPE</a>



<a href="..\wwan\ne-wwan-_wwan_ussd_session_state.md">WWAN_USSD_SESSION_STATE</a>



<a href="..\wwan\ns-wwan-_wwan_ussd_string.md">WWAN_USSD_STRING</a>



 

 


