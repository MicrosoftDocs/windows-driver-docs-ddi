---
UID: NF:ntddk.RtlDrainNonVolatileFlush
title: RtlDrainNonVolatileFlush function (ntddk.h)
description: The routine RtlDrainNonVolatileFlush waits for the flushes initiated by RtlFlushNonVolatileMemory to finish.
old-location: ifsk\rtldrainnonvolatileflush.htm
tech.root: ifsk
ms.assetid: EA1C2DF3-591C-407A-ABBF-DE615466A498
ms.date: 04/16/2018
ms.keywords: RtlDrainNonVolatileFlush, RtlDrainNonVolatileFlush routine [Installable File System Drivers], ifsk.rtldrainnonvolatileflush, ntddk/RtlDrainNonVolatileFlush
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- RtlDrainNonVolatileFlush
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlDrainNonVolatileFlush function


## -description


The routine <b>RtlDrainNonVolatileFlush</b> waits for the flushes initiated by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-rtlflushnonvolatilememory">RtlFlushNonVolatileMemory</a>
    to finish.


## -parameters




### -param NvToken [in]

 A pointer to an opaque structure that has
        information about various properties of the non-volatile memory region which <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-rtlgetnonvolatiletoken">RtlGetNonVolatileToken</a> had returned.


## -returns



The routine <b>RtlDrainNonVolatileFlush</b> returns one of the following:

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



 This routine <b>RtlDrainNonVolatileFlush</b> can also add more context to <b>NvToken</b> to help verifiers. This routine is currently not supported for Windows Server until the next major release of Windows Server.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-rtlflushnonvolatilememory">
RtlFlushNonVolatileMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-rtlflushnonvolatilememoryranges">RtlFlushNonVolatileMemoryRanges</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-rtlfreenonvolatiletoken">RtlFreeNonVolatileToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-rtlgetnonvolatiletoken">RtlGetNonVolatileToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-rtlwritenonvolatilememory">RtlWriteNonVolatileMemory</a>
 

 

