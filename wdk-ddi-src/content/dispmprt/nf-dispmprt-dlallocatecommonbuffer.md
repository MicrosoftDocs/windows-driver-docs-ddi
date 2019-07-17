---
UID: NF:dispmprt.DlAllocateCommonBuffer
title: DlAllocateCommonBuffer function
author: windows-driver-content
description: Allocates and maps a logically contiguous region of memory that is simultaneously accessible both from the processor and from a device.
tech.root: display
ms.assetid: dc2f64dc-204a-41c5-af32-341e7dd06782
ms.author: windowsdriverdev
ms.date: 04/04/2019 
ms.topic: function
f1_keywords:
 - "dispmprt/DlAllocateCommonBuffer"
ms.keywords: DlAllocateCommonBuffer
req.header: dispmprt.h
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
- DllExport
api_location: 
- DispLib.dll
- DispLib.dll
api_name: 
- DlAllocateCommonBuffer
product: 
- Windows
targetos: Windows
ms.custom: 19H1
---

# DlAllocateCommonBuffer function


## -description

Allocates and maps a logically contiguous region of memory that is simultaneously accessible both from the processor and from a device.

## -parameters

### -param DeviceHandle

Handle to the device.

### -param DlpDmaAdapter

Display library direct memory access adapter.

### -param DesiredLength

Specifies the requested number of bytes of memory.

### -param LogicalAddress

Pointer to a memory location that receives the logical address to be used by the adapter to access the allocated buffer.

### -param CacheEnabled

Specifies whether the allocated memory can be cached.

### -param Reserved

Is currently ignored by the video port driver.


## -returns

This function returns PVOID.

## -remarks

## -see-also
