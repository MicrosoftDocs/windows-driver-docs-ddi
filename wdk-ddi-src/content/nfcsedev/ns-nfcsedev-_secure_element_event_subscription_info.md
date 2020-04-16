---
UID: NS:nfcsedev._SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO
title: _SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO (nfcsedev.h)
description: The SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO structure is an input parameter to IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT.
old-location: nfpdrivers\secure_element_event_subscription_info.htm
tech.root: nfpdrivers
ms.assetid: 1ADA8430-86B4-4885-B20A-EBA8CDAC5449
ms.date: 02/15/2018
keywords: ["_SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO structure"]
ms.keywords: "*PSECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO, PSECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO, PSECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO structure pointer [Near-Field Proximity Drivers], SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO, SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO structure [Near-Field Proximity Drivers], _SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO, nfcsedev/PSECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO, nfcsedev/SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO, nfpdrivers.secure_element_event_subscription_info"
f1_keywords:
 - "nfcsedev/SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- nfcsedev.h
api_name:
- SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO
product:
- Windows
targetos: Windows
req.typenames: SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO, *PSECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO
---

# _SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO structure


## -description


The SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO structure is an input parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfcsedev/ni-nfcsedev-ioctl_nfcse_subscribe_for_event">IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT</a>.


## -struct-fields




### -field guidSecureElementId


### -field eEventType

Secure element event type. A service can subscribe and receive notification when an external reader arrival, external reader departure, transaction, HCE activated, or HCE deactivated event is triggered.

