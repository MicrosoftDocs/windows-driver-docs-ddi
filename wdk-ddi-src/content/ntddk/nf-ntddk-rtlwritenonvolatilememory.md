---
UID: NF:ntddk.RtlWriteNonVolatileMemory
title: RtlWriteNonVolatileMemory function (ntddk.h)
description: The routine RtlWriteNonVolatileMemory copies the contents of a source buffer to a non-volatile destination memory buffer.
old-location: ifsk\rtlwritenonvolatilememory.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RtlWriteNonVolatileMemory function"]
ms.keywords: RtlWriteNonVolatileMemory, RtlWriteNonVolatileMemory routine [Installable File System Drivers], ifsk.rtlwritenonvolatilememory, ntddk/RtlWriteNonVolatileMemory
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
 - RtlWriteNonVolatileMemory
 - ntddk/RtlWriteNonVolatileMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - RtlWriteNonVolatileMemory
---

# RtlWriteNonVolatileMemory function


## -description

The routine <b>RtlWriteNonVolatileMemory</b> copies the contents of a source buffer to a non-volatile destination memory buffer.

## -parameters

### -param NvToken

 A pointer to an opaque structure that has
        information about various properties of the non-volatile memory region which <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlgetnonvolatiletoken">RtlGetNonVolatileToken</a> had returned.

### -param NvDestination

A pointer to the non-volatile destination buffer to copy to.

### -param Source

A pointer to the source buffer to copy from.

### -param Size

The length, in bytes, of the copy operation.

### -param Flags

Reserved for future use.

## -returns

The routine <b>RtlWriteNonVolatileMemory</b> returns one of the following:

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

 This is a <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcopymemory">RtlCopyMemory</a> equivalent for non-volatile memory
    the value add is only with verifier enabled. When the verifier is enabled,
    ranges that are modified can be tracked in <b>NvToken</b> and can be reported
    in <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlfreenonvolatiletoken">RtlFreeNonVolatileToken</a> if a flush is not called for a write. This routine is currently not supported for Windows Server until the next major release of Windows Server.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcopymemory">RtlCopyMemory</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtldrainnonvolatileflush">RtlDrainNonVolatileFlush</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlflushnonvolatilememory">
RtlFlushNonVolatileMemory</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlflushnonvolatilememoryranges">RtlFlushNonVolatileMemoryRanges</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlfreenonvolatiletoken">RtlFreeNonVolatileToken</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlgetnonvolatiletoken">RtlGetNonVolatileToken</a>
