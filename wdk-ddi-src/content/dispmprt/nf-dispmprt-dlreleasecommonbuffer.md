---
UID: NF:dispmprt.DlReleaseCommonBuffer
title: DlReleaseCommonBuffer function
description: Frees a common buffer that was previously allocated.
tech.root: display
ms.date: 04/04/2019
keywords: ["DlReleaseCommonBuffer function"]
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
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - DlReleaseCommonBuffer
 - dispmprt/DlReleaseCommonBuffer
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - Displib.lib
 - Displib.dll
api_name:
 - DlReleaseCommonBuffer
dev_langs:
 - c++
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

## -remarks

## -see-also

