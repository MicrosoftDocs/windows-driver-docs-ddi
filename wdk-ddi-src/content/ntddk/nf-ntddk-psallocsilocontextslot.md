---
UID: NF:ntddk.PsAllocSiloContextSlot
title: PsAllocSiloContextSlot function
author: windows-driver-content
description: This routine allocates a slot that can be used to insert, retrieve, and delete an object in all silos. .
old-location: kernel\psallocsilocontextslot.htm
old-project: kernel
ms.assetid: 835446D1-EB41-47BC-AA0F-54A9C029EFFE
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PsAllocSiloContextSlot routine [Kernel-Mode Driver Architecture], kernel.psallocsilocontextslot, PsAllocSiloContextSlot, ntddk/PsAllocSiloContextSlot
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
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
-	PsAllocSiloContextSlot
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsAllocSiloContextSlot function


## -description


This routine allocates a slot that can be used to insert, retrieve, and delete an object in all silos. 


## -syntax


````
NTSTATUS PsAllocSiloContextSlot(
  _In_  ULONG_PTR Reserved,
  _Out_ ULONG     *ReturnedContextSlot
);
````


## -parameters




### -param Reserved [in]

This parameter is reserved for future use and <b>must be set to zero</b>. 
<div class="alert"><b>Warning</b>  Setting <i>Reserved</i> to a non-zero value causes the system to execute an <b>ASSERT</b> on a checked build.</div><div> </div>

### -param ReturnedContextSlot [out]

A pointer to a caller-allocated variable that receives the newly allocated slot index. This parameter is required and it cannot be <b>NULL</b>.


## -returns


The following NT status codes are returned.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES </b></dt>
</dl>
</td>
<td width="60%">
There are no more slots available in the system. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
</table> 



## -remarks


Use of this API is uncommon because all silo monitors are assigned a storage slot when calling the <a href="..\ntddk\nf-ntddk-psregistersilomonitor.md">PsRegisterSiloMonitor</a> routine.  That slot can be retrieved with the <a href="..\ntddk\nf-ntddk-psgetsilomonitorcontextslot.md">PsGetSiloMonitorContextSlot</a> routine and used by a driver for its context operations.



## -see-also

<a href="..\ntddk\nf-ntddk-psfreesilocontextslot.md">PsFreeSiloContextSlot</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsAllocSiloContextSlot routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

