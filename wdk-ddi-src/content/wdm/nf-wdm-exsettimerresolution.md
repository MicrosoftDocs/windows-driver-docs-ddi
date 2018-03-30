---
UID: NF:wdm.ExSetTimerResolution
title: ExSetTimerResolution function
author: windows-driver-content
description: The ExSetTimerResolution routine modifies the frequency at which the system clock interrupts. Use this routine with extreme caution (see the following Remarks section).
old-location: kernel\exsettimerresolution.htm
old-project: kernel
ms.assetid: 968d57fa-7a8e-42cf-b73b-d669ecbbaf48
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ExSetTimerResolution, ExSetTimerResolution routine [Kernel-Mode Driver Architecture], k102_09179649-af93-434f-92e0-844a2bdf34dc.xml, kernel.exsettimerresolution, wdm/ExSetTimerResolution
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExApcLte2, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExSetTimerResolution
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExSetTimerResolution function


## -description


The <b>ExSetTimerResolution</b> routine modifies the frequency at which the system clock interrupts. <u>Use this routine with extreme caution (see the following Remarks section).</u>


## -parameters




### -param DesiredTime [in]

Specifies the amount of time that should elapse between each timer interrupt, in 100-nanosecond units. The minimum value is approximately 10,000 (1 millisecond) but can vary slightly by platform. (This parameter is ignored if <i>SetResolution</i> is <b>FALSE</b>.) 


### -param SetResolution [in]

If <b>TRUE</b>, the call is a request to set the clock interrupt frequency to the value specified by <i>DesiredTime</i>. If <b>FALSE</b>, the call is a request to restore the clock interrupt frequency to the system's default value, which is platform-specific. 


## -returns



<b>ExSetTimerResolution</b> returns the new timer resolution, in 100-nanosecond units.




## -remarks



To set the timer resolution, a driver calls this routine passing <b>TRUE</b> as the parameter for <i>SetResolution</i>. The following rules apply:

<ul>
<li>
The routine changes the clock interrupt frequency <u>only</u> if the specified  <i>DesiredTime</i> value is less than the current setting.

</li>
<li>
If a driver requests a <i>DesiredTime</i> value that is greater than what is currently set, the routine just returns the current setting.

</li>
<li>
If a driver requests a <i>DesiredTime</i> value that is less than the system clock can support, the routine uses the smallest resolution the system can support, and returns that value.

</li>
</ul>
If you use this routine to change the clock interrupt frequency, your driver <u>must</u> restore the default interrupt frequency, typically by making the following call before being unloaded:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>ExSetTimerResolution (0, FALSE);</pre>
</td>
</tr>
</table></span></div>
(If multiple drivers have attempted to modify the clock interrupt frequency, the system does not restore the default frequency until all of these drivers have called this routine with a <i>SetResolution</i> value of <b>FALSE</b>.)

<u>Note that the result of changing the clock interrupt frequency is system-wide and can have a severely negative effect on system performance. Also note that higher clock interrupt frequencies can shorten a system's battery life.</u>

During the processing of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550784">IRP_MJ_POWER</a> request, the power manager holds a lock on a resource that <b>ExSetTimerResolution</b> must acquire to complete. Consequently, a deadlock will occur if a driver directly or indirectly calls <b>ExSetTimerResolution</b> while processing a power request, and then waits for the call to <b>ExSetTimerResolution</b> to return before the driver completes the power request. For more information about safely calling <b>ExSetTimerResolution</b> while processing a power IRP, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540721">Calling ExSetTimerResolution While Processing a Power IRP</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553292">KeSetTimerEx</a>
 

 

