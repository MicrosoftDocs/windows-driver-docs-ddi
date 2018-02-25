---
UID: NF:strmini.StreamClassCallAtNewPriority
title: StreamClassCallAtNewPriority function
author: windows-driver-content
description: The StreamClassCallAtNewPriority routine schedules a routine to be called at a different priority.
old-location: stream\streamclasscallatnewpriority.htm
old-project: stream
ms.assetid: 86c4e9da-7c71-4d79-b8e2-f602489da647
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , A, C, N, P, S, StreamClassCallAtNewPriority, StreamClassCallAtNewPriority routine [Streaming Media Devices], a, e, i, l, m, o, r, s, strclass-routines_6335ceee-08a1-4078-a9ce-aaa15d8158cd.xml, stream.streamclasscallatnewpriority, strmini/StreamClassCallAtNewPriority, t, w, y"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: "(See Parameters section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Stream.lib
-	Stream.dll
apiname:
-	StreamClassCallAtNewPriority
product: Windows
targetos: Windows
req.typenames: STREAM_PRIORITY, *PSTREAM_PRIORITY
req.product: Windows 10 or later.
---

# StreamClassCallAtNewPriority function


## -description


The <b>StreamClassCallAtNewPriority</b> routine schedules a routine to be called at a different priority.


## -syntax


````
VOID StreamClassCallAtNewPriority(
  _In_opt_ PHW_STREAM_OBJECT    StreamObject,
  _In_     PVOID                HwDeviceExtension,
  _In_     STREAM_PRIORITY      Priority,
  _In_     PHW_PRIORITY_ROUTINE PriorityRoutine,
  _In_     PVOID                Context
);
````


## -parameters




### -param StreamObject [in, optional]

Pointer to an HW_STREAM_OBJECT structure specifying the stream is associated with the routine, or <b>NULL</b> if the routine is associated with the device as a whole. There can be only one routine per stream, and only one routine for the device. This parameter is optional.


### -param HwDeviceExtension [in]

Pointer to the minidriver's device extension. The minidriver specifies the size of this buffer in the <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="https://msdn.microsoft.com/library/windows/hardware/ff568263">StreamClassRegisterMinidriver</a>. The class driver then passes pointers to the buffer in the <b>HwDeviceExtension</b> member of the <a href="..\strmini\ns-strmini-_hw_stream_request_block.md">HW_STREAM_REQUEST_BLOCK</a>, <a href="..\strmini\ns-strmini-_hw_stream_object.md">HW_STREAM_OBJECT</a>, <a href="..\strmini\ns-strmini-_hw_time_context.md">HW_TIME_CONTEXT</a>, and <a href="..\storport\ns-storport-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> structures it passes to the minidriver.


### -param Priority [in]

Specifies one of the values listed in the following table.

<table>
<tr>
<th>Priority</th>
<th>Usage</th>
</tr>
<tr>
<td>
High

</td>
<td>
The stream class driver calls the routine at the same priority as the minidriver's <b>StrMini</b><i>Xxx</i> callbacks. Do not use this setting unless the routine must be synchronized with the minidriver's interrupt service routine.

</td>
</tr>
<tr>
<td>
Dispatch

</td>
<td>
The stream class driver calls the routine at DISPATCH_LEVEL. Use this priority if the routine takes less than 1 millisecond to complete.

</td>
</tr>
<tr>
<td>
Low

</td>
<td>
The stream class driver calls the routine at PASSIVE_LEVEL. Use this priority if the routine takes less than 1 millisecond to complete.

</td>
</tr>
<tr>
<td>
LowToHigh

</td>
<td>
Used to allow a thread called at low priority to return to high priority so that other stream class driver services can be called.

</td>
</tr>
</table>
 


### -param PriorityRoutine [in]

Pointer to a minidriver-supplied <a href="..\strmini\nc-strmini-phw_priority_routine.md">StrMiniPriorityRoutine</a> to be called at the specified priority level.


### -param Context [in]

Specifies the parameter to be passed to the <i>PriorityRoutine</i>.


## -returns



None



