---
UID: NF:storport.StorPortInitializeTimer
title: StorPortInitializeTimer function
author: windows-driver-content
description: Creates a Storport timer context object.
old-location: storage\storportinitializetimer.htm
tech.root: storage
ms.assetid: 1F43EEDC-5DB4-4ABE-BBC6-A4A51FCAF0B6
ms.date: 3/29/2018
ms.keywords: StorPortInitializeTimer, StorPortInitializeTimer routine [Storage Devices], storage.storportinitializetimer, storport/StorPortInitializeTimer
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
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortInitializeTimer
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortInitializeTimer function


## -description


Creates a Storport timer context object.


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



Storport provides a single timer to a miniport driver by using the  <b>RequestTimerCall</b> notification type in <a href="https://msdn.microsoft.com/library/windows/hardware/ff567433">StorPortNotification</a>. If a miniport requires more than one timer, additional timers are created with <b>StorPortInitializeTimer</b>.

It is recommended that miniports call <b>StorPortInitializeTimer</b> in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557390">HwStorFindAdapter</a> function to ensure that the additional timer resources are available.

Miniports can use this routine to set coalescing timers to create a delay period after an initial timeout.

Prior to Windows 8, a maximum of 4 timers can be created with <b>StorPortInitializeTimer</b>.
Starting with Windows 8, there is no maximum timers limitation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557390">HwStorFindAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451476">StorPortFreeTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567433">StorPortNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451511">StorPortRequestTimer</a>
 

 

