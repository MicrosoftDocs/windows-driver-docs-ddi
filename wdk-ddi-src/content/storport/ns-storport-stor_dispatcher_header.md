---
UID: NS:storport._STOR_DISPATCHER_HEADER
title: STOR_DISPATCHER_HEADER
author: windows-driver-content
description: The STOR_DISPATCHER_HEADER structure is an opaque structure that describes a dispatcher object.
tech.root: storage
ms.assetid: f6864a1e-ea64-4daa-bbe6-d658d03f37cf
ms.author: windowsdriverdev
ms.date: 03/24/2020
ms.topic: struct
ms.keywords: STOR_DISPATCHER_HEADER, STOR_DISPATCHER_HEADER, *PSTOR_DISPATCHER_HEADER,
req.header: storport.h
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
req.typenames: STOR_DISPATCHER_HEADER, *PSTOR_DISPATCHER_HEADER
targetos: Windows
f1_keywords:
 - _STOR_DISPATCHER_HEADER
 - storport/_STOR_DISPATCHER_HEADER
 - PSTOR_DISPATCHER_HEADER
 - storport/PSTOR_DISPATCHER_HEADER
 - STOR_DISPATCHER_HEADER
 - storport/STOR_DISPATCHER_HEADER
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
---

# STOR_DISPATCHER_HEADER structure


## -description

The **STOR_DISPATCHER_HEADER** structure is an opaque structure that describes a dispatcher object.

## -struct-fields

### -field Data

Reserved for system use.

### -field Data.Type

Reserved for system use.

### -field Data.Flags

Reserved for system use.

### -field Data.Size

Reserved for system use.

### -field Data.Inserted

Reserved for system use.

### -field Data.DebugActive

Reserved for system use.

### -field Lock

Reserved for system use.

### -field SignalState

Reserved for system use.

### -field WaitListHead

Reserved for system use.

## -remarks

**STOR_DISPATCHER_HEADER** is a member of the [**STOR_EVENT**](ns-storport-stor_event.md) structure that is passed to [**StorPortInitializeEvent**](nf-storport-storportinitializeevent.md) and [**StorPortSetEvent**](nf-storport-storportsetevent.md).

## -see-also

[**KeInitializeEvent**](../wdm/nf-wdm-keinitializeevent.md)
[STOR_EVENT](ns-storport-stor_event.md)

[**StorPortInitializeEvent**](nf-storport-storportinitializeevent.md)

[**StorPortSetEvent**](nf-storport-storportsetevent.md)