---
UID: NF:ndis.NET_BUFFER_FIRST_MDL
title: NET_BUFFER_FIRST_MDL macro (ndis.h)
description: NET_BUFFER_FIRST_MDL is a macro that NDIS drivers use to get the first MDL in a NET_BUFFER structure.
tech.root: netvista
ms.assetid: 64e87615-2466-4f52-adb7-b98bec2f0252
ms.date: 04/12/2018
ms.topic: macro
ms.keywords: NET_BUFFER_FIRST_MDL
req.header: ndis.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ndis.h
api_name: 
-	NET_BUFFER_FIRST_MDL
product:
-	Windows
targetos: Windows

---

# NET_BUFFER_FIRST_MDL macro


## -description

**NET_BUFFER_FIRST_MDL** is a macro that NDIS drivers use to get the first MDL in a [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -parameters

### -param _NB

A pointer to a **NET_BUFFER** structure.

## -returns

**NET_BUFFER_FIRST_MDL** returns a pointer to the first MDL in a linked list of MDLs that is associated with the indicated [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -remarks

**NET_BUFFER_FIRST_MDL** gets the return value from the **MdlChain** member of the [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -see-also

[**NET_BUFFER**](ns-ndis-_net_buffer.md)
