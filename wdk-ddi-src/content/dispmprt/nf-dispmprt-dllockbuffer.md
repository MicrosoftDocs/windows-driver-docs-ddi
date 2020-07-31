---
UID: NF:dispmprt.DlLockBuffer
title: DlLockBuffer function
author: windows-driver-content
description: Probes the specified buffer, makes the buffer's memory pages resident in memory, and locks the physical pages mapped by the virtual address range.
tech.root: display
ms.assetid: 660bfe14-da4e-400b-92ea-b432a1147346
ms.author: windowsdriverdev
ms.date: 04/04/2019 
keywords: ["DlLockBuffer function"]
f1_keywords:
 - "dispmprt/DlLockBuffer"
 - "DlLockBuffer"
ms.keywords: DlLockBuffer
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
- DlLockBuffer
product: 
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# DlLockBuffer function


## -description

Probes the specified buffer, makes the buffer's memory pages resident in memory, and locks the physical pages mapped by the virtual address range.

## -parameters

### -param DeviceHandle

A handle that represents a display adapter.

### -param BaseAddress

Specifies the virtual address of the buffer to be locked.

### -param Length

Specifies the length in bytes of the buffer to be locked.

### -param Operation

Specifies the type of operation for which the caller wants the access rights probed and the pages locked.


## -returns

This function returns PVOID.

## -remarks

## -see-also
