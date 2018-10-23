---
UID: NF:storport.StorPortRequestTimer
title: StorPortRequestTimer function
author: windows-driver-content
description: Schedules a callback event for a Storport timer context object.
old-location: storage\storportrequesttimer.htm
tech.root: storage
ms.assetid: EE5A6D39-EC76-4D97-B2EC-4A43225C2FB5
ms.date: 03/29/2018
ms.keywords: StorPortRequestTimer, StorPortRequestTimer routine [Storage Devices], storage.storportrequesttimer, storport/StorPortRequestTimer
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
req.irql: Any
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortRequestTimer
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortRequestTimer function


## -description


Schedules a callback event for a Storport timer context object.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param TimerHandle [in]

A pointer to an opaque buffer for the timer context returned by <a href="https://msdn.microsoft.com/library/windows/hardware/hh451483">StorPortInitializeTimer</a>.


### -param TimerCallback [in]

A pointer to a timer callback routine supplied by the miniport. The following is the prototype defined for <b>PHW_TIMER_EX</b>:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
(*PHW_TIMER_EX) (
  _In_ PVOID  DeviceExtension,
  _In_opt_ PVOID Context
  );</pre>
</td>
</tr>
</table></span></div>

### -param CallbackContext [in, optional]

A pointer to a miniport provided context for the timer callback.


### -param TimerValue [in]

The timeout value for the timer, in microseconds. Setting <i>TimerValue</i> to 0 will cancel the timer.


### -param TolerableDelay [in]

The allowable delay for the timer in microseconds. Values less than 32 microseconds are ignored and <i>TolerableDelay</i> defaults to 0.


## -returns



The <b>StorPortRequestTimer</b> routine returns one of these status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Not enough resources available to defer scheduling of the timer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
<i>HwDeviceExtension</i>, <i>TimerHandle</i>, or <i>TimerCallback</i> is NULL.

The timer context object, <i>TimerHandle</i>, is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_BUSY</b></dt>
</dl>
</td>
<td width="60%">
A previous timer request is active. <i>TimerValue</i> &gt; 0 and <i>TimerCallback</i> has not been called.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The timer request was successfully scheduled.

</td>
</tr>
</table>
 




## -remarks



The <b>StorPortRequestTimer</b> routine is callable at any IRQL. However, if the routine is called when IRQL &gt; DISPATCH_LEVEL, the timer's scheduling is deferred until IRQL &lt;= DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557426">HwStorTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451476">StorPortFreeTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451483">StorPortInitializeTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567433">StorPortNotification</a>
 

 

