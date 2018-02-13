---
UID: NF:storport.StorPortRequestTimer
title: StorPortRequestTimer function
author: windows-driver-content
description: Schedules a callback event for a Storport timer context object.
old-location: storage\storportrequesttimer.htm
old-project: storage
ms.assetid: EE5A6D39-EC76-4D97-B2EC-4A43225C2FB5
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storport/StorPortRequestTimer, StorPortRequestTimer routine [Storage Devices], storage.storportrequesttimer, StorPortRequestTimer
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
req.irql: Any
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
-	StorPortRequestTimer
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortRequestTimer function


## -description


Schedules a callback event for a Storport timer context object.


## -syntax


````
ULONG StorPortRequestTimer(
  _In_     PVOID        HwDeviceExtension,
  _In_     PVOID        TimerHandle,
  _In_     PHW_TIMER_EX TimerCallback,
  _In_opt_ PVOID        CallbackContext,
  _In_     LONGLONG     TimerValue,
  _In_     LONGLONG     TolerableDelay
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param TimerHandle [in]

A pointer to an opaque buffer for the timer context returned by <a href="..\storport\nf-storport-storportinitializetimer.md">StorPortInitializeTimer</a>.


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

<a href="..\storport\nf-storport-storportnotification.md">StorPortNotification</a>



<a href="..\storport\nf-storport-storportinitializetimer.md">StorPortInitializeTimer</a>



<a href="..\storport\nf-storport-storportfreetimer.md">StorPortFreeTimer</a>



<a href="..\storport\nc-storport-hw_timer.md">HwStorTimer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortRequestTimer routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

