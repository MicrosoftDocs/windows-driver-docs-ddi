---
UID: NF:ntddk.RtlFlushNonVolatileMemory
title: RtlFlushNonVolatileMemory function
author: windows-driver-content
description: The routine RtlFlushNonVolatileMemory optimally flushes the given non-volatile memory region.
old-location: ifsk\rtlflushnonvolatilememory.htm
tech.root: ifsk
ms.assetid: 759CDFAA-D939-44E7-AE03-E3ED90F8E09D
ms.date: 04/16/2018
ms.keywords: RtlFlushNonVolatileMemory, RtlFlushNonVolatileMemory routine [Installable File System Drivers], ifsk.rtlflushnonvolatilememory, ntddk/RtlFlushNonVolatileMemory
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	RtlFlushNonVolatileMemory
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
        information about various properties of the non-volatile memory region which <a href="https://msdn.microsoft.com/A9E866D4-C47F-4926-A838-EDB739CF1185">RtlGetNonVolatileToken</a> had returned.


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




<a href="https://msdn.microsoft.com/EA1C2DF3-591C-407A-ABBF-DE615466A498">RtlDrainNonVolatileFlush</a>



<a href="https://msdn.microsoft.com/169C5F41-B372-4056-AAC5-53DD0582A563">RtlFlushNonVolatileMemoryRanges</a>



<a href="https://msdn.microsoft.com/8E083814-7408-47D2-A811-2DCBDCD13097">RtlFreeNonVolatileToken</a>



<a href="https://msdn.microsoft.com/A9E866D4-C47F-4926-A838-EDB739CF1185">RtlGetNonVolatileToken</a>



<a href="https://msdn.microsoft.com/49DDDEF8-F949-4674-A18B-9BB091D163C2">RtlWriteNonVolatileMemory</a>
 

 

