---
UID: NS:ks.__unnamed_struct_74
title: KSDPC_ITEM (ks.h)
description: The KSDPC_ITEM structure is used to store information related to any internal DPCs that might be used to generate event notification from a raised IRQL.
old-location: stream\ksdpc_item.htm
tech.root: stream
ms.assetid: 7732b1a8-4f76-49d0-acbf-ce0be6b36858
ms.date: 04/23/2018
keywords: ["KSDPC_ITEM structure"]
ms.keywords: "*PKSDPC_ITEM, KSDPC_ITEM, KSDPC_ITEM structure [Streaming Media Devices], PKSDPC_ITEM, PKSDPC_ITEM structure pointer [Streaming Media Devices], ks-struct_c40f10e3-5732-4020-a22f-4695eaaa471a.xml, ks/KSDPC_ITEM, ks/PKSDPC_ITEM, stream.ksdpc_item"
f1_keywords:
 - "ks/KSDPC_ITEM"
 - "KSDPC_ITEM"
req.header: ks.h
req.include-header: Ks.h
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
- ks.h
api_name:
- KSDPC_ITEM
targetos: Windows
req.typenames: KSDPC_ITEM, *PKSDPC_ITEM
---

# KSDPC_ITEM structure


## -description


The KSDPC_ITEM structure is used to store information related to any internal DPCs that might be used to generate event notification from a raised IRQL.


## -struct-fields




### -field Dpc

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KDPC</a> structure that is queued to perform notifications that cannot occur at raised IRQL.


### -field ReferenceCount

Specifies whether pending DPCs will reference this structure. This is initially set to 1 when the event structure is created, and decremented when the event structure is destroyed. If the reference count is nonzero at that time, then the last DPC to run frees the structure rather than the event disable call.


### -field AccessLock

This lock is used to synchronize deletion of an event item with any DPC that might be running.


## -remarks



KSDPC_ITEM uses a reference counting scheme to determine when to free the structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KDPC</a>
 

 

