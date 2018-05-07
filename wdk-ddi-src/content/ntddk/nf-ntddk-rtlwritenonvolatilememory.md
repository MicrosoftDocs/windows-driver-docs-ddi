---
UID: NF:ntddk.RtlWriteNonVolatileMemory
title: RtlWriteNonVolatileMemory function
author: windows-driver-content
description: The routine RtlWriteNonVolatileMemory copies the contents of a source buffer to a non-volatile destination memory buffer.
old-location: ifsk\rtlwritenonvolatilememory.htm
old-project: ifsk
ms.assetid: 49DDDEF8-F949-4674-A18B-9BB091D163C2
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RtlWriteNonVolatileMemory, RtlWriteNonVolatileMemory routine [Installable File System Drivers], ifsk.rtlwritenonvolatilememory, ntddk/RtlWriteNonVolatileMemory
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	RtlWriteNonVolatileMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlWriteNonVolatileMemory function


## -description


The routine <b>RtlWriteNonVolatileMemory</b> copies the contents of a source buffer to a non-volatile destination memory buffer.


## -parameters




### -param NvToken

 A pointer to an opaque structure that has
        information about various properties of the non-volatile memory region which <a href="https://msdn.microsoft.com/A9E866D4-C47F-4926-A838-EDB739CF1185">RtlGetNonVolatileToken</a> had returned.


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



 This is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561808">RtlCopyMemory</a> equivalent for non-volatile memory
    the value add is only with verifier enabled. When the verifier is enabled,
    ranges that are modified can be tracked in <b>NvToken</b> and can be reported
    in <a href="https://msdn.microsoft.com/8E083814-7408-47D2-A811-2DCBDCD13097">RtlFreeNonVolatileToken</a> if a flush is not called for a write. This routine is currently not supported for Windows Server until the next major release of Windows Server.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561808">RtlCopyMemory</a>



<a href="https://msdn.microsoft.com/EA1C2DF3-591C-407A-ABBF-DE615466A498">RtlDrainNonVolatileFlush</a>



<a href="https://msdn.microsoft.com/759CDFAA-D939-44E7-AE03-E3ED90F8E09D">
RtlFlushNonVolatileMemory</a>



<a href="https://msdn.microsoft.com/169C5F41-B372-4056-AAC5-53DD0582A563">RtlFlushNonVolatileMemoryRanges</a>



<a href="https://msdn.microsoft.com/8E083814-7408-47D2-A811-2DCBDCD13097">RtlFreeNonVolatileToken</a>



<a href="https://msdn.microsoft.com/A9E866D4-C47F-4926-A838-EDB739CF1185">RtlGetNonVolatileToken</a>
 

 

