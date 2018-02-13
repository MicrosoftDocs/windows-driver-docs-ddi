---
UID: NF:storport.StorPortInitializeTimer
title: StorPortInitializeTimer function
author: windows-driver-content
description: Creates a Storport timer context object.
old-location: storage\storportinitializetimer.htm
old-project: storage
ms.assetid: 1F43EEDC-5DB4-4ABE-BBC6-A4A51FCAF0B6
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortInitializeTimer routine [Storage Devices], storport/StorPortInitializeTimer, StorPortInitializeTimer, storage.storportinitializetimer
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
-	StorPortInitializeTimer
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortInitializeTimer function


## -description


Creates a Storport timer context object.


## -syntax


````
ULONG StorPortInitializeTimer(
  _In_  PVOID HwDeviceExtension,
  _Out_ PVOID *TimerHandle
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param TimerHandle [out]

A pointer to an opaque buffer that holds context information for the timer.


## -returns



The <b>StorPortInitializeTimer</b> routine returns one of these status codes:

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
 Insufficient resources are available to initialize the timer context.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The timer context was successfully initialized.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The number of supported timers is exceeded.

</td>
</tr>
</table>
 




## -remarks



Storport provides a single timer to a miniport driver by using the  <b>RequestTimerCall</b> notification type in <a href="..\storport\nf-storport-storportnotification.md">StorPortNotification</a>. If a miniport requires more than one timer, additional timers are created with <b>StorPortInitializeTimer</b>.

It is recommended that miniports call <b>StorPortInitializeTimer</b> in the <a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a> function to ensure that the additional timer resources are available.

Miniports can use this routine to set coalescing timers to create a delay period after an initial timeout.

Prior to Windows 8, a maximum of 4 timers can be created with <b>StorPortInitializeTimer</b>.
Starting with Windows 8, there is no maximum timers limitation.




## -see-also

<a href="..\storport\nf-storport-storportfreetimer.md">StorPortFreeTimer</a>



<a href="..\storport\nf-storport-storportnotification.md">StorPortNotification</a>



<a href="..\storport\nf-storport-storportrequesttimer.md">StorPortRequestTimer</a>



<a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortInitializeTimer routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

