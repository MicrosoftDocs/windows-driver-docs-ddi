---
UID: NF:sensorsutils.CollectionsListDeserializeFromBuffer
title: CollectionsListDeserializeFromBuffer function (sensorsutils.h)
description: This routine deserializes a collection list from the input buffer.
ms.assetid: db498ec5-520f-4850-b596-a178e9c7540c
ms.date: 08/07/2018
keywords: ["CollectionsListDeserializeFromBuffer function"]
tech.root: sensors
ms.keywords: CollectionsListDeserializeFromBuffer
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
targetos: Windows
ms.custom: RS5
f1_keywords:
 - CollectionsListDeserializeFromBuffer
 - sensorsutils/CollectionsListDeserializeFromBuffer
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - sensorsutils.h
api_name:
 - CollectionsListDeserializeFromBuffer
---

# CollectionsListDeserializeFromBuffer function


## -description

This routine deserializes a collection list from the input buffer.

## -parameters

### -param SourceBufferSizeInBytes

[in] The input buffer size (in bytes).

### -param SourceBuffer

[in] A buffer containing the serialized collection list data.

### -param TargetCollection

[in/out] The caller-allocated collection list with AllocatedSizeInBytes set to the allocation size.

## -returns

This function returns NTSTATUS.

## -remarks

## -see-also

