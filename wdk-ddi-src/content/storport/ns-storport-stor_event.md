---
UID: NS:storport._STOR_EVENT
title: STOR_EVENT
author: windows-driver-content
description: The STOR_EVENT structure describes an event object.
tech.root: storage
ms.assetid: e97bff93-6b37-4ecb-9b3a-9a0be475ae87
ms.author: windowsdriverdev
ms.date: 03/24/2020
ms.topic: struct
ms.keywords: STOR_EVENT, STOR_EVENT, *PSTOR_EVENT, *PRSTOR_EVENT, 
req.header: storport.h
f1_keywords:
 - "storport/STOR_EVENT"
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: STOR_EVENT, *PSTOR_EVENT, *PRSTOR_EVENT
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - storport.h
api_name: 
 - STOR_EVENT
product: 
 - Windows
targetos: Windows
---

# STOR_EVENT structure

## -description

The **STOR_EVENT** structure describes an event object.

## -struct-fields

### -field Header

An opaque [**STOR_DISPATCHER_HEADER**](ns-storport-stor_dispatcher_event.md) structure that describes an event object.

## -remarks

Callers of [**StorPortInitializeEvent**](nf-storport-storportinitializeevent.md) must first allocate space for a **STOR_EVENT** structure.

## -see-also

[**KeInitializeEvent**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializeevent)
[STOR_EVENT](ns-storport-stor_event.md)

[**STOR_DISPATCHER_HEADER**](ns-storport-stor_dispatcher_event.md)

[**StorPortInitializeEvent**](nf-storport-storportinitializeevent.md)

[**StorPortSetEvent**](nf-storport-storportsetevent.md)
