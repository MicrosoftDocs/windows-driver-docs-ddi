---
UID: NF:sensorsutils.CollectionsListAllocateBufferAndSerialize
title: CollectionsListAllocateBufferAndSerialize function
author: windows-driver-content
description: This routine allocates a buffer and then serializes a sensor collection list to it.
ms.assetid: be6b18b4-97cf-4206-ad98-57a045ecd11f
ms.author: windowsdriverdev
ms.date: 08/07/18
ms.topic: function
ms.prod: windows-hardware
ms.technology: windows-devices
tech.root: sensors
ms.keywords: CollectionsListAllocateBufferAndSerialize
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
-	apiref
api_type: 
-	LibDef
api_location: 
-	sensorsutils.h
api_name: 
-	CollectionsListAllocateBufferAndSerialize
product:
 - Windows
targetos: Windows


---

# CollectionsListAllocateBufferAndSerialize function


## -description

This routine allocates a buffer and then serializes a sensor collection list to it. On success, callers must use [SerializationBufferFree](nf-sensorsutils-serializationbufferfree.md) to free the buffer.


## -parameters

### -param SourceCollection

[in] Pointer to a collection list.

### -param pTargetBufferSizeInBytes

[out] The allocated buffer size (in bytes).

### -param pTargetBuffer

[out] Pointer to the allocated buffer, to hold the serialized data.

## -returns

This function returns NTSTATUS.

## -remarks

## -see-also