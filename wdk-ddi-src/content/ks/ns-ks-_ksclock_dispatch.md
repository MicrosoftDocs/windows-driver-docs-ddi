---
UID: NS:ks._KSCLOCK_DISPATCH
title: "_KSCLOCK_DISPATCH"
author: windows-driver-content
description: The KSCLOCK_DISPATCH structure contains the callbacks required for a pin to implement a clock object.
old-location: stream\ksclock_dispatch.htm
old-project: stream
ms.assetid: cc9b7049-7b43-4c66-9d08-93af22d92540
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PKSCLOCK_DISPATCH, KSCLOCK_DISPATCH, KSCLOCK_DISPATCH structure [Streaming Media Devices], PKSCLOCK_DISPATCH, PKSCLOCK_DISPATCH structure pointer [Streaming Media Devices], _KSCLOCK_DISPATCH, avstruct_5015e5e6-b0c5-4eb9-9e04-8631e732f8be.xml, ks/KSCLOCK_DISPATCH, ks/PKSCLOCK_DISPATCH, stream.ksclock_dispatch"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSCLOCK_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: KSCLOCK_DISPATCH, *PKSCLOCK_DISPATCH
---

# _KSCLOCK_DISPATCH structure


## -description


The KSCLOCK_DISPATCH structure contains the callbacks required for a pin to implement a clock object.


## -struct-fields




### -field SetTimer

Optionally contains a pointer to an alternate function to use in generating DPC timer callbacks based on a presentation time. If this is set, this function is used to set timers based on deltas to the current presentation time in order to generate event notifications. If an alternate function is specified to set timers, a corresponding <b>CancelTimer</b> function must also be provided. This is set to <b>NULL</b> if the default <a href="https://msdn.microsoft.com/library/windows/hardware/ff553292">KeSetTimerEx</a> function is used to approximate the next notification time. This would normally be set only if a <b>KeSetTimerEx</b> function was being used. The function must have the same characteristics as the default function.

The function should be prototyped as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  BOOLEAN SetTimer (IN PKSPIN Pin,
    IN PKTIMER Timer,
    IN LARGE_INTEGER DueTime,
    IN PKDPC Dpc);</pre>
</td>
</tr>
</table></span></div>
See the documentation for <b>KeSetTimerEx</b> for details on implementation of this function. Any client implementation must behave in a similar manner.


### -field CancelTimer

Optionally contains an alternate function to use in canceling outstanding timer callbacks. If an alternate function is provided to cancel timers, a corresponding <i>SetTimer</i> function must also be provided. This is set to <b>NULL</b> if the default <b>KeCancelTimer</b> function is to be used. The function must have the same characteristics as the default function.

The function should be prototyped as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  BOOLEAN CancelTimer (IN PKSPIN Pin,
    IN PKTIMER Timer);</pre>
</td>
</tr>
</table></span></div>
See the documentation for <b>KeCancelTimer</b> for details on the implementation of this function. Any client implementation must behave in a similar manner.


### -field CorrelatedTime

A pointer to a function to retrieve the current clock time and a correlated system time as an atomic operation. The function should be prototyped as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  LONGLONG CorrelatedTime (IN PKSPIN Pin,
    OUT PLONGLONG SystemTime);</pre>
</td>
</tr>
</table></span></div>
The current clock time should be returned and the current system time should be placed in <b>SystemTime</b>.


### -field Resolution

A pointer to a function to specify the resolution of the clock. This corresponds to the KS property <a href="https://msdn.microsoft.com/library/windows/hardware/ff565092">KSPROPERTY_CLOCK_RESOLUTION</a>. This function should report the granularity in terms of 100-nanosecond units. For more information, see the KS documentation on KSPROPERTY_CLOCK_RESOLUTION. 

The function should be prototyped as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    void Resolution (IN PKSPIN Pin,
        OUT PKSRESOLUTION Resolution);</pre>
</td>
</tr>
</table></span></div>

## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563535">KSPIN_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565092">KSPROPERTY_CLOCK_RESOLUTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566806">KSRESOLUTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553292">KeSetTimerEx</a>
 

 

