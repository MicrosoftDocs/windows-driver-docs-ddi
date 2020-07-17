---
UID: NF:ntddk.RtlFlushNonVolatileMemory
title: RtlFlushNonVolatileMemory function (ntddk.h)
description: The routine RtlFlushNonVolatileMemory optimally flushes the given non-volatile memory region.
old-location: ifsk\rtlflushnonvolatilememory.htm
tech.root: ifsk
ms.assetid: 759CDFAA-D939-44E7-AE03-E3ED90F8E09D
ms.date: 04/16/2018
keywords: ["RtlFlushNonVolatileMemory function"]
ms.keywords: RtlFlushNonVolatileMemory, RtlFlushNonVolatileMemory routine [Installable File System Drivers], ifsk.rtlflushnonvolatilememory, ntddk/RtlFlushNonVolatileMemory
f1_keywords:
 - "ntddk/RtlFlushNonVolatileMemory"
 - "RtlFlushNonVolatileMemory"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- RtlFlushNonVolatileMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlFlushNonVolatileMemory function


## -description


The  routine <b>RtlFlushNonVolatileMemory</b> optimally flushes the given non-volatile memory region.


## -parameters




### -param NvToken

 A pointer to an opaque structure that has
        information about various properties of the non-volatile memory region which <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlgetnonvolatiletoken">RtlGetNonVolatileToken</a> had returned.


### -param NvBuffer

A pointer to the non-volatile memory to flush. This should be user addresses obtained from
        a file mapping object.


### -param Size

The length, in bytes, of the non-volatile memory buffer <b>NvBuffer</b> points to.


### -param Flags

One of the following flags can be specified:

<table>
<tr>
<th>Flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FLUSH_NV_MEMORY_IN_FLAG_NO_DRAIN

</td>
<td>
Specifies that this routine does not need to wait for the flush to drain.

</td>
</tr>
</table>
 


## -returns



The routine <b>RtlFreeNonVolatileToken</b> returns one of the status codes:

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



 This routine <b>RtlFlushNonVolatileMemory</b> can also add more context to <b>NvToken</b> to help verifiers. This routine is currently not supported for Windows Server until the next major release of Windows Server. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtldrainnonvolatileflush">RtlDrainNonVolatileFlush</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlflushnonvolatilememoryranges">RtlFlushNonVolatileMemoryRanges</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlfreenonvolatiletoken">RtlFreeNonVolatileToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlgetnonvolatiletoken">RtlGetNonVolatileToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlwritenonvolatilememory">RtlWriteNonVolatileMemory</a>
 

 

