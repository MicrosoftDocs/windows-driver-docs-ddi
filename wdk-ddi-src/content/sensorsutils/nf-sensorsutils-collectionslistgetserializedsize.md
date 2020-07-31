---
UID: NF:sensorsutils.CollectionsListGetSerializedSize
title: CollectionsListGetSerializedSize function (sensorsutils.h)
description: This routine returns the larger of the two sizes to provide for sufficient buffer sizes to accommodate passing the collection list across processes that can have different bit-ness values.
ms.assetid: e5b38220-cc8d-425c-b1a8-d61983d36e2a
ms.date: 08/08/2018
keywords: ["CollectionsListGetSerializedSize function"]
f1_keywords:
 - "sensorsutils/CollectionsListGetSerializedSize"
 - "CollectionsListGetSerializedSize"
tech.root: sensors
ms.keywords: CollectionsListGetSerializedSize
req.header: sensorsutils.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
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
- apiref
api_type: 
- LibDef
api_location: 
- sensorsutils.h
api_name: 
- CollectionsListGetSerializedSize
targetos: Windows


ms.custom: RS5
---

# CollectionsListGetSerializedSize function


## -description

This routine returns the larger of the two sizes to provide for sufficient buffer sizes to accommodate passing the collection list across processes that can have different bit-ness values (e.g. 32 bit <-> 64 bit):

1. The architecture-independent size of the entire collection list, including size of memory blocks that are pointed by embedded pointers.
2. The RPC serialized size of the collection list.

## -parameters

### -param Collection

[in] Pointer to a collection list.

## -returns

This function returns a ULONG that represents the serialized data size.

## -remarks

## -see-also
