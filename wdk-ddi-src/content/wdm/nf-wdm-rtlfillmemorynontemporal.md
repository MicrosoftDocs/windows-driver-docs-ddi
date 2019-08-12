---
UID: NF:wdm.RtlFillMemoryNonTemporal
title: RtlFillMemoryNonTemporal function
author: windows-driver-content
description: This function fills a block of memory with the specified fill value using non-temporal moves that do not pollute the cache.
tech.root:
ms.assetid: dd55904e-f4ba-4501-9cb8-d653376ebb2f
ms.author: windowsdriverdev
ms.date: 
ms.topic: function
f1_keywords:
 - "wdm/RtlFillMemoryNonTemporal"
ms.keywords: RtlFillMemoryNonTemporal
req.header: wdm.h
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
- wdm.h
api_name: 
- RtlFillMemoryNonTemporal
product: 
- Windows
targetos: Windows

ms.custom: 19H1
---

# RtlFillMemoryNonTemporal function


## -description

This function fills a block of memory with the specified fill value using non-temporal moves that do not pollute the cache.

## -parameters

### -param Destination

A pointer to the destination memory block to copy the bytes to.

### -param Length

The number of bytes to copy from the source to the destination.

### -param Value

The value to fill the destination memory block with. This value is copied to every byte in the memory block that is defined by *Destination* and *Length*.


## -returns
This function returns NTSYSAPI VOID.
## -remarks

**RtlFillMemoryNonTemporal** only performs a non-temporal fill for x64-based systems, and only when the *Length* parameter is 8 bytes or greater. Otherwise, this function is equivalent to [**RtlFillMemory**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlfillmemory).

## -see-also

[**RtlFillMemory**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlfillmemory)
