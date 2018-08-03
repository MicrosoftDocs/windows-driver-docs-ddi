---
UID: NF:ntddk.RtlGetNonVolatileToken
title: RtlGetNonVolatileToken function
author: windows-driver-content
description: The routine, RtlGetNonVolatileToken, gets various properties about a non-volatile memory buffer and stores them in the variable NvToken.
old-location: ifsk\rtlgetnonvolatiletoken.htm
tech.root: ifsk
ms.assetid: A9E866D4-C47F-4926-A838-EDB739CF1185
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RtlGetNonVolatileToken, RtlGetNonVolatileToken routine [Installable File System Drivers], ifsk.rtlgetnonvolatiletoken, ntddk/RtlGetNonVolatileToken
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
-	RtlGetNonVolatileToken
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlGetNonVolatileToken function


## -description


The routine, <b>RtlGetNonVolatileToken</b>, gets various properties about a non-volatile memory
    buffer and stores them in the variable <b>NvToken</b>.


## -parameters




### -param NvBuffer

A pointer to the non-volatile memory that the returned <b>NvToken</b> is going to track state for. This should be an address obtained from a file mapping object.


### -param Size

The length, in bytes, of the non-volatile memory buffer <b>NvBuffer</b> points to.


### -param NvToken

 A pointer to an opaque structure that tracks
        information about the given non-volatile memory region which <b>RtlGetNonVolatileToken</b> had returned.


## -returns



The routine <b>RtlGetNonVolatileToken</b> returns one of the status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller had insufficient access rights to perform the requested action.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH
</b></dt>
</dl>
</td>
<td width="60%">
The specified base address is outside the range of accessible addresses.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <b>NvBuffer</b> is not the same length as specified in<b>Size</b>.

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




<a href="https://msdn.microsoft.com/EA1C2DF3-591C-407A-ABBF-DE615466A498">RtlDrainNonVolatileFlush</a>



<a href="https://msdn.microsoft.com/759CDFAA-D939-44E7-AE03-E3ED90F8E09D">
RtlFlushNonVolatileMemory</a>



<a href="https://msdn.microsoft.com/169C5F41-B372-4056-AAC5-53DD0582A563">RtlFlushNonVolatileMemoryRanges</a>



<a href="https://msdn.microsoft.com/8E083814-7408-47D2-A811-2DCBDCD13097">RtlFreeNonVolatileToken</a>



<a href="https://msdn.microsoft.com/49DDDEF8-F949-4674-A18B-9BB091D163C2">RtlWriteNonVolatileMemory</a>
 

 

