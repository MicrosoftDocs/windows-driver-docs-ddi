---
UID: NF:ntddk.RtlFlushNonVolatileMemoryRanges
title: RtlFlushNonVolatileMemoryRanges function (ntddk.h)
description: The routine RtlFlushNonVolatileMemoryRanges optimally flushes the given non-volatile memory regions.
old-location: ifsk\rtlflushnonvolatilememoryranges.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RtlFlushNonVolatileMemoryRanges function"]
ms.keywords: RtlFlushNonVolatileMemoryRanges, RtlFlushNonVolatileMemoryRanges routine [Installable File System Drivers], ifsk.rtlflushnonvolatilememoryranges, ntddk/RtlFlushNonVolatileMemoryRanges
req.header: ntddk.h
req.include-header: Winnt.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlFlushNonVolatileMemoryRanges
 - ntddk/RtlFlushNonVolatileMemoryRanges
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - RtlFlushNonVolatileMemoryRanges
---

# RtlFlushNonVolatileMemoryRanges function


## -description

The routine <b>RtlFlushNonVolatileMemoryRanges</b> optimally flushes the given non-volatile memory regions.

## -parameters

### -param NvToken

 A pointer to an opaque structure that has
        information about various properties of the non-volatile memory region which <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlgetnonvolatiletoken">RtlGetNonVolatileToken</a> had returned.

### -param NvRanges

Specifies an array of <b>NV_MEMORY_RANGE</b> structures which describe the non-volatile memory regions to flush

### -param NumRanges

<p>Specifies the number of elements in the <b>NVRanges</b> array.</p>

### -param Flags

For flags specified, refer <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlflushnonvolatilememory">RtlFlushNonVolatileMemory</a> as this routine also honors the flags apart from passing it to <b>RtlFlushNonVolatileMemory</b>.

## -returns

The routine <b>RtlFlushNonVolatileMemoryRanges</b> returns one of the following:

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

This routine is currently not supported for Windows Server until the next major release of Windows Server.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtldrainnonvolatileflush">RtlDrainNonVolatileFlush</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlflushnonvolatilememory">
RtlFlushNonVolatileMemory</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlfreenonvolatiletoken">RtlFreeNonVolatileToken</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlgetnonvolatiletoken">RtlGetNonVolatileToken</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlwritenonvolatilememory">RtlWriteNonVolatileMemory</a>
