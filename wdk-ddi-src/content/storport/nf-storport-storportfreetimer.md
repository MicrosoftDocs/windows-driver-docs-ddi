---
UID: NF:storport.StorPortFreeTimer
title: StorPortFreeTimer function
author: windows-driver-content
description: Frees a Storport timer context object previously created by the StorPortInitializeTimer routine.
old-location: storage\storportfreetimer.htm
old-project: storage
ms.assetid: AF6B1693-6242-4F09-8226-472E75B809F3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.storportfreetimer, StorPortFreeTimer routine [Storage Devices], StorPortFreeTimer, storport/StorPortFreeTimer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
-	StorPortFreeTimer
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortFreeTimer function


## -description


Frees a Storport timer context object previously created by the <a href="..\storport\nf-storport-storportinitializetimer.md">StorPortInitializeTimer</a> routine.


## -syntax


````
ULONG StorPortFreeTimer(
  _In_ PVOID HwDeviceExtension,
  _In_ PVOID TimerHandle
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param TimerHandle [in]

A pointer to an opaque buffer for the timer context returned by <a href="..\storport\nf-storport-storportinitializetimer.md">StorPortInitializeTimer</a>.


## -returns



The <b>StorPortFreeTimer</b> routine returns one of these status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>
</td>
<td width="60%">
Current IRQL &gt; DISPATCH_LEVEL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Either <i>HwDeviceExtension</i> or <i>TimerHandle</i> is NULL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Insufficient resources are available to free the timer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The timer was successfully freed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The timer is already free.

</td>
</tr>
</table>
 




## -remarks



Miniports should call <b>StorPortFreeTimer</b> whenever a work item is no longer needed or when the miniport receives a PnP SRB notification  that the adapter is removed.




## -see-also

<a href="..\storport\nc-storport-hw_adapter_control.md">HwStorAdapterControl</a>



<a href="..\storport\nf-storport-storportinitializetimer.md">StorPortInitializeTimer</a>



<a href="..\storport\nf-storport-storportrequesttimer.md">StorPortRequestTimer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortFreeTimer routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

