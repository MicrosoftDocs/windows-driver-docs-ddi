---
UID: NF:ntddstor.RtlZeroMemory
title: RtlZeroMemory macro (ntddstor.h)
description: The RtlZeroMemory routine fills a block of memory with zeros, given a pointer to the block and the length, in bytes, to be filled.
ms.assetid: c45de332-ebef-43d7-b1ce-852c08291127
ms.date: 09/20/2018
ms.topic: macro
ms.keywords: RtlZeroMemory
req.header: ntddstor.h
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
- HeaderDef
api_location: 
- ntddstor.h
api_name: 
- RtlZeroMemory
product:
- Windows
targetos: Windows

---

# RtlZeroMemory macro


## -description

The <b>RtlZeroMemory</b> routine fills a block of memory with zeros, given a pointer to the block and the length, in bytes, to be filled.

## -parameters

### -param Destination

Datatype: void*. A pointer to the memory block to be filled with zeros.

### -param Length

Datatype: size_t. The number of bytes to fill with zeros.


## -remarks

To zero out a memory buffer to erase security-sensitive data, use <a href="..\wdm\nf-wdm-rtlsecurezeromemory.md">RtlSecureZeroMemory</a> instead.

Callers of <b>RtlZeroMemory</b> can be running at any IRQL if the destination memory block is in nonpaged system memory. Otherwise, the caller must be running at IRQL &lt;= APC_LEVEL.

## -see-also

<a href="..\wdm\nf-wdm-rtlfillmemory.md">RtlFillMemory</a>



<a href="..\wdm\nf-wdm-rtlsecurezeromemory.md">RtlSecureZeroMemory</a>To zero out a memory buffer to erase security-sensitive data, use <a href="..\wdm\nf-wdm-rtlsecurezeromemory.md">RtlSecureZeroMemory</a> instead.
