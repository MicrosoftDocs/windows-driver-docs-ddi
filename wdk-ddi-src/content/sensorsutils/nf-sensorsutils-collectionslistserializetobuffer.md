---
UID: NF:sensorsutils.CollectionsListSerializeToBuffer
title: CollectionsListSerializeToBuffer function (sensorsutils.h)
description: This routine serializes a collection list to the caller-allocated buffer.
ms.assetid: 5006837d-7e09-4dad-b7ef-927b69d67a25
ms.date: 08/08/2018
ms.topic: function
tech.root: sensors
ms.keywords: CollectionsListSerializeToBuffer
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
- CollectionsListSerializeToBuffer
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# CollectionsListSerializeToBuffer function


## -description

This routine serializes a collection list to the caller-allocated buffer.

## -parameters

### -param SourceCollection

[in] Pointer to a collection list.

### -param TargetBufferSizeInBytes

[in] Caller-allocated buffer size (in bytes).

### -param TargetBuffer

[out] Caller-allocated buffer to hold the serialized data.

## -returns

This function returns NTSTATUS.

## -remarks

## -see-also
