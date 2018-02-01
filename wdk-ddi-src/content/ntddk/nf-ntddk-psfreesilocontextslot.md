---
UID: NF:ntddk.PsFreeSiloContextSlot
title: PsFreeSiloContextSlot function
author: windows-driver-content
description: This routine frees the specified slot and makes it available in the system. It undoes the effects of the PsAllocSiloContextSlot routine.
old-location: kernel\psfreesilocontextslot.htm
old-project: kernel
ms.assetid: 659B92A6-8582-468F-8CDD-119832A95230
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.psfreesilocontextslot, PsFreeSiloContextSlot, PsFreeSiloContextSlot routine [Kernel-Mode Driver Architecture], ntddk/PsFreeSiloContextSlot
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
-	PsFreeSiloContextSlot
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsFreeSiloContextSlot function


## -description


This routine  frees the specified slot and makes it available in the system. It undoes the effects of the  <a href="..\ntddk\nf-ntddk-psallocsilocontextslot.md">PsAllocSiloContextSlot</a> routine.


## -syntax


````
NTSTATUS PsFreeSiloContextSlot(
  _In_ ULONG ContextSlot
);
````


## -parameters




### -param ContextSlot [in]

A slot allocated by the <a href="..\ntddk\nf-ntddk-psallocsilocontextslot.md">PsAllocSiloContextSlot</a> routine. 
<div class="alert"><b>Warning</b>  Setting this parameter to a slot that is still in use causes the system to execute bug check.</div><div> </div>

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
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The slot is not allocated in the system. This is an error code.

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



## -see-also

<a href="..\ntddk\nf-ntddk-psallocsilocontextslot.md">PsAllocSiloContextSlot</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsFreeSiloContextSlot routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

