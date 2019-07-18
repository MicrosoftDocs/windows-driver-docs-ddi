---
UID: NF:dispmprt.DlReleaseCommonBuffer
title: DlReleaseCommonBuffer function
author: windows-driver-content
description: Frees a common buffer that was previously allocated.
tech.root: display
ms.assetid: 22d1c24f-83d9-4c1d-982f-813af2aff9db
ms.author: windowsdriverdev
ms.date: 04/04/2019 
ms.topic: function
f1_keywords:
 - "dispmprt/DlReleaseCommonBuffer"
ms.keywords: DlReleaseCommonBuffer
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
- Displib.lib
- Displib.dll
api_name: 
- DlReleaseCommonBuffer
product: 
- Windows
targetos: Windows

ms.custom: 19H1
---

# DlReleaseCommonBuffer function


## -description

Frees a common buffer that was previously allocated.

## -parameters

### -param DeviceHandle

A handle that represents a display adapter.

### -param DlpDmaAdapter



### -param Length

Specifies the number of bytes of memory to be freed.

### -param LogicalAddress

Specifies the logical address of the buffer to be freed.

### -param VirtualAddress

Pointer to the corresponding virtual address of the allocated memory range.

### -param CacheEnabled

Indicates whether the allocated memory is cached.


## -returns

This function returns VOID.

## -remarks

## -see-also
