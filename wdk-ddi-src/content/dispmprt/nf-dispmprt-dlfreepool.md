---
UID: NF:dispmprt.DlFreePool
title: DlFreePool function
description: Deallocates a block of pool memory previously allocated by the DlAllocatePool function.
tech.root: display
ms.date: 04/04/2019
keywords: ["DlFreePool function"]
ms.keywords: DlFreePool
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
 - DlFreePool
 - dispmprt/DlFreePool
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - Displib.lib
 - Displib.dll
api_name:
 - DlFreePool
product:
 - Windows
dev_langs:
 - c++
---

# DlFreePool function


## -description

Deallocates a block of pool memory previously allocated by the [DlAllocatePool](nf-dispmprt-dlallocatepool.md) function.

## -parameters

### -param DeviceHandle

A handle that represents a display adapter.

### -param Ptr

Pointer to a memory pool.

## -remarks

## -see-also

