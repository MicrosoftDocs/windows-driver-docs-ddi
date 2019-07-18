---
UID: NF:dispmprt.DlFreePool
title: DlFreePool function
author: windows-driver-content
description: Deallocates a block of pool memory previously allocated by the DlAllocatePool function.
tech.root: display
ms.assetid: d925a8ec-9878-4089-985d-cc58863dbd96
ms.author: windowsdriverdev
ms.date: 04/04/2019 
ms.topic: function
f1_keywords:
 - "dispmprt/DlFreePool"
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
targetos: Windows

ms.custom: 19H1
---

# DlFreePool function


## -description

Deallocates a block of pool memory previously allocated by the [DlAllocatePool](nf-dispmprt-dlallocatepool.md) function.

## -parameters

### -param DeviceHandle

A handle that represents a display adapter.

### -param Ptr

Pointer to a memory pool.


## -returns

This function returns VOID.

## -remarks

## -see-also
