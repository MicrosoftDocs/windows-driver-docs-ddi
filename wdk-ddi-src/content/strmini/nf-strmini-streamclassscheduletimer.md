---
UID: NF:strmini.StreamClassScheduleTimer
title: StreamClassScheduleTimer function (strmini.h)
description: The minidriver calls the StreamClassScheduleTimer routine to schedule a timer, and to specify a routine that is called when the timer expires.
old-location: stream\streamclassscheduletimer.htm
tech.root: stream
ms.assetid: 83271c19-911b-481a-bc25-c0b3816cf800
ms.date: 04/23/2018
ms.keywords: StreamClassScheduleTimer, StreamClassScheduleTimer routine [Streaming Media Devices], strclass-routines_73f92fc4-e9bf-40af-8dff-9c2e740dba20.xml, stream.streamclassscheduletimer, strmini/StreamClassScheduleTimer
ms.topic: function
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: Stream.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Stream.lib
- Stream.dll
api_name:
- StreamClassScheduleTimer
product:
- Windows
targetos: Windows
req.typenames: 
---

# StreamClassScheduleTimer function


## -description


The minidriver calls the <b>StreamClassScheduleTimer</b> routine to schedule a timer, and to specify a routine that is called when the timer expires.


## -parameters




### -param StreamObject [in, optional]

Specifies the stream that sets the timer, or <b>NULL</b> if the timer is set for the whole driver. The minidriver may only schedule one timer per stream, and one for the driver as a whole. This parameter is optional.


### -param HwDeviceExtension [in]

Pointer to the minidriver's device extension. The minidriver specifies the size of this buffer in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559682">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="https://msdn.microsoft.com/library/windows/hardware/ff568263">StreamClassRegisterMinidriver</a>. The class driver then passes pointers to the buffer in the <b>HwDeviceExtension</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559702">HW_STREAM_REQUEST_BLOCK</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff559697">HW_STREAM_OBJECT</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff559706">HW_TIME_CONTEXT</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff567785">PORT_CONFIGURATION_INFORMATION</a> structures it passes to the minidriver.


### -param NumberOfMicroseconds [in]

Specifies the amount of time, in microseconds, before the timer expires.


### -param TimerRoutine [in]

Specifies the routine called when the timer expires. The routine's prototype must be of the form:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    TimerRoutine(PVOID Context);</pre>
</td>
</tr>
</table></span></div>

### -param Context [in]

Pointer to a context that the class driver passes to the callback routine once the timer expires.


## -returns



None



