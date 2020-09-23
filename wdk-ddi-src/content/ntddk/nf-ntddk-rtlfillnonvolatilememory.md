---
UID: NF:ntddk.RtlFillNonVolatileMemory
title: RtlFillNonVolatileMemory function
description: Fills the non-volatile destination buffer with the given value.
tech.root: 
ms.assetid: 4126cd43-dfd3-4d78-ba6c-192ece10aa2d
ms.date: 08/19/2019
keywords: ["RtlFillNonVolatileMemory function"]
ms.keywords: RtlFillNonVolatileMemory
req.header: ntddk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: DPC_LEVEL
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
 - RtlFillNonVolatileMemory
 - ntddk/RtlFillNonVolatileMemory
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - ntddk.h
api_name:
 - RtlFillNonVolatileMemory
product:
 - Windows
---

# RtlFillNonVolatileMemory function


## -description

The routine <b>RtlFillNonVolatileMemory</b> fills the non-volatile destination buffer with the given value.

## -parameters

### -param NvToken

A pointer to an opaque structure that has more information about the non-volatile memory region which <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlgetnonvolatiletoken">RtlGetNonVolatileToken</a> had returned.

### -param NvDestination

A pointer to the non-volatile destination buffer.

### -param Size

Specifies the length, in bytes, of the fill operation.

### -param Value

A UCHAR containing the value with which to fill the destination buffer.

### -param Flags

A value of type ULONG containing one or more of the following flags:

| Flags  | Meaning  |
|---|---|
|  FILL_NV_MEMORY_FLAG_FLUSH | Set the provided value, then flush the destination range. Unless FILL_NV_MEMORY_FLAG_NO_DRAIN is specified, the flush is followed by a drain. This flag ensures that the data is durable even in the event of system power loss. |
|  FILL_NV_MEMORY_FLAG_NON_TEMPORAL |  Perform a non-temporal memset when available.  Non-temporal means that data caching is not required.  If the processor does not support non-temporal operations for ranges smaller than address bus size, perform a regular memset followed by flush and drain. If the processor ignores non-temporal moves altogether, RtlSetNonVolatileMemory doesn't replace it with flush and drain.  However, if Windows doesn't haven an implementation for a given architecture (say ARM64), replace it with flush and drain.  |
| FILL_NV_MEMORY_FLAG_PERSIST  |  Makes sure that the memset is persisted either by flushing or using non-temporal moves. Typically, the system uses the approach that is least costly to persist the data. This flag makes sure that the data is durable even in case of system power loss.  Ignored when FILL_NV_MEMORY_FLAG_PERSIST is specified. |
| FILL_NV_MEMORY_FLAG_NO_DRAIN  |  Tells the routine not to wait for the flush to complete. Must be specified in conjunction with FILL_NV_MEMORY_FLAG_FLUSH and without FILL_NV_MEMORY_FLAG_PERSIST or FILL_NV_MEMORY_FLAG_NON_TEMPORAL.  |

## -returns

The routine returns one of the status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
<b>NvToken</b> is an invalid pointer or token.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The request was successful.

</td>
</tr>
</table>

## -remarks

## -see-also