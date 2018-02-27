---
UID: NF:ntddk.RtlDrainNonVolatileFlush
title: RtlDrainNonVolatileFlush function
author: windows-driver-content
description: The routine RtlDrainNonVolatileFlush waits for the flushes initiated by RtlFlushNonVolatileMemory to finish.
old-location: ifsk\rtldrainnonvolatileflush.htm
old-project: ifsk
ms.assetid: EA1C2DF3-591C-407A-ABBF-DE615466A498
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlDrainNonVolatileFlush, RtlDrainNonVolatileFlush routine [Installable File System Drivers], ifsk.rtldrainnonvolatileflush, ntddk/RtlDrainNonVolatileFlush
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	RtlDrainNonVolatileFlush
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# RtlDrainNonVolatileFlush function


## -description


The routine <b>RtlDrainNonVolatileFlush</b> waits for the flushes initiated by <a href="..\ntddk\nf-ntddk-rtlflushnonvolatilememory.md">RtlFlushNonVolatileMemory</a>
    to finish.


## -syntax


````
NTSTATUS RtlDrainNonVolatileFlush(
  _In_ PVOID NvToken
);
````


## -parameters




### -param NvToken [in]

 A pointer to an opaque structure that has
        information about various properties of the non-volatile memory region which <a href="..\ntddk\nf-ntddk-rtlgetnonvolatiletoken.md">RtlGetNonVolatileToken</a> had returned.


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

<a href="https://msdn.microsoft.com/49DDDEF8-F949-4674-A18B-9BB091D163C2">RtlWriteNonVolatileMemory</a>



<a href="https://msdn.microsoft.com/759CDFAA-D939-44E7-AE03-E3ED90F8E09D">
RtlFlushNonVolatileMemory</a>



<a href="https://msdn.microsoft.com/8E083814-7408-47D2-A811-2DCBDCD13097">RtlFreeNonVolatileToken</a>



<a href="https://msdn.microsoft.com/169C5F41-B372-4056-AAC5-53DD0582A563">RtlFlushNonVolatileMemoryRanges</a>



<a href="https://msdn.microsoft.com/A9E866D4-C47F-4926-A838-EDB739CF1185">RtlGetNonVolatileToken</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlDrainNonVolatileFlush routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

