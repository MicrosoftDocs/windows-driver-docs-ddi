---
UID: NS:nfcsedev._SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO
title: _SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO
author: windows-driver-content
description: The SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO structure is an input parameter to IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT.
old-location: nfpdrivers\secure_element_event_subscription_info.htm
old-project: nfpdrivers
ms.assetid: 1ADA8430-86B4-4885-B20A-EBA8CDAC5449
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: _SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO, *PSECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO, SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO
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
req.alt-api: SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO
req.alt-loc: nfcsedev.h
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
req.typenames: *PSECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO, SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO
---

# _SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO structure



## -description
The SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO structure is an input parameter to <a href="..\nfcsedev\ni-nfcsedev-ioctl_nfcse_subscribe_for_event.md">IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT</a>.



## -syntax

````
typedef struct _SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO {
  GUID                      guidSecureElementId;
  SECURE_ELEMENT_EVENT_TYPE eEventType;
} SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO, *PSECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO;
````


## -struct-fields

### -field guidSecureElementId


### -field eEventType

Secure element event type. A service can subscribe and receive notification when an external reader arrival, external reader departure, transaction, HCE activated, or HCE deactivated event is triggered.


## -remarks
