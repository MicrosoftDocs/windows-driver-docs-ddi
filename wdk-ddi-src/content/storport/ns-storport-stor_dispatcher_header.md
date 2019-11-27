---
UID: NS:storport._STOR_DISPATCHER_HEADER
title: STOR_DISPATCHER_HEADER
author: windows-driver-content
description: 
tech.root: storage
ms.assetid: f6864a1e-ea64-4daa-bbe6-d658d03f37cf
ms.author: windowsdriverdev
ms.date: 12/15/2019
ms.topic: struct
ms.keywords: STOR_DISPATCHER_HEADER, STOR_DISPATCHER_HEADER, *PSTOR_DISPATCHER_HEADER, 
req.header: storport.h
f1_keywords:
 - "storport/STOR_DISPATCHER_HEADER"
req.include-header:
req.target-type:
req.target-min-winverclnt: The next version of Windows 10
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: STOR_DISPATCHER_HEADER, *PSTOR_DISPATCHER_HEADER
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - storport.h
api_name: 
 - STOR_DISPATCHER_HEADER
product: 
 - Windows
targetos: Windows
---

# STOR_DISPATCHER_HEADER structure

## -description

The STOR_DISPATCHER_HEADER structure ??????????????????????????????

## -struct-fields

### -field Data


### -field Data.Type


### -field Data.Flags


### -field Data.Size


### -field Data.Inserted


### -field Data.DebugActive


### -field Lock


### -field SignalState


### -field WaitListHead

## -remarks

STOR_DISPATCHER_HEADER is a member of the [STOR_EVENT](ns-storport-stor_event.md) structure that is passed to [**StorPortInitializeEvent**](nf-storport-storportinitializeevent.md) and [**StorPortSetEvent**](nf-storport-storportsetevent.md).

<!-- how is it initialized? -->

## -see-also

[STOR_EVENT](ns-storport-stor_event.md)

[**StorPortInitializeEvent**](nf-storport-storportinitializeevent.md)

[**StorPortSetEvent**](nf-storport-storportsetevent.md)
