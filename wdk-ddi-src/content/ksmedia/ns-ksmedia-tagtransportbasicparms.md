---
UID: NS:ksmedia.tagTRANSPORTBASICPARMS
title: tagTRANSPORTBASICPARMS
author: windows-driver-content
description: The TRANSPORTBASICPARMS structure is defined but not used.
old-location: stream\transportbasicparms.htm
old-project: stream
ms.assetid: 40e305b3-e91c-4227-99e7-dbb939082f54
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: TRANSPORTBASICPARMS structure [Streaming Media Devices], PTRANSPORTBASICPARMS structure pointer [Streaming Media Devices], ksmedia/PTRANSPORTBASICPARMS, PTRANSPORTBASICPARMS, tagTRANSPORTBASICPARMS, vidcapstruct_5a5cdf6a-56f3-43ad-9bab-e5d406052707.xml, *PTRANSPORTBASICPARMS, stream.transportbasicparms, ksmedia/TRANSPORTBASICPARMS, TRANSPORTBASICPARMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	TRANSPORTBASICPARMS
product: Windows
targetos: Windows
req.typenames: "*PTRANSPORTBASICPARMS, TRANSPORTBASICPARMS"
---

# tagTRANSPORTBASICPARMS structure


## -description


The TRANSPORTBASICPARMS structure is defined but not used.


## -syntax


````
typedef struct tagTRANSPORTBASICPARMS {
  LONG  TimeFormat;
  LONG  TimeReference;
  LONG  Superimpose;
  LONG  EndStopAction;
  LONG  RecordFormat;
  LONG  StepFrames;
  LONG  SetpField;
  LONG  Preroll;
  LONG  RecPreroll;
  LONG  Postroll;
  LONG  EditDelay;
  LONG  PlayTCDelay;
  LONG  RecTCDelay;
  LONG  EditField;
  LONG  FrameServo;
  LONG  ColorFrameServo;
  LONG  ServoRef;
  LONG  WarnGenlock;
  LONG  SetTracking;
  TCHAR VolumeName[40];
  LONG  Ballistic[20];
  LONG  Speed;
  LONG  CounterFormat;
  LONG  TunerChannel;
  LONG  TunerNumber;
  LONG  TimerEvent;
  LONG  TimerStartDay;
  LONG  TimerStartTime;
  LONG  TimerStopDay;
  LONG  TimerStopTime;
} TRANSPORTBASICPARMS, *PTRANSPORTBASICPARMS;
````


## -struct-fields




#### - TimeFormat

Indicates the basic time format.
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
ED_FORMAT_MILLISECONDS

</td>
<td>
Milliseconds

</td>
</tr>
<tr>
<td>
ED_FORMAT_FRAMES

</td>
<td>
Frames

</td>
</tr>
<tr>
<td>
ED_FORMAT_REFERENCE_TIME

</td>
<td>
Reference time

</td>
</tr>
<tr>
<td>
ED_FORMAT_HMSF

</td>
<td>
Binary coded decimal, representing hours, minutes, seconds, and frames

</td>
</tr>
<tr>
<td>
ED_FORMAT_TMSF

</td>
<td>
Binary coded decimal, representing tracks, minutes, seconds, and frames

</td>
</tr>
</table> 


#### - TimeReference

Indicates the basic time reference.
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
ED_TIMEREF_TIMECODE

</td>
<td>
Time code

</td>
</tr>
<tr>
<td>
ED_TIMEREF_CONTROL_TRACK

</td>
<td>
Control track

</td>
</tr>
<tr>
<td>
ED_TIMEREF_INDEX

</td>
<td>
Index

</td>
</tr>
</table> 


#### - Superimpose

Indicates whether to enable or disable the onscreen display. Specify <b>TRUE</b> to enable, <b>FALSE</b> to disable.


#### - EndStopAction

Specifies the stop action.
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
ED_MODE_STOP

</td>
<td>
Stop

</td>
</tr>
<tr>
<td>
ED_MODE_REWIND

</td>
<td>
Rewind

</td>
</tr>
<tr>
<td>
ED_MODE_FREEZE

</td>
<td>
Freeze/pause

</td>
</tr>
</table> 


#### - RecordFormat

Indicates the basic record format.
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
ED_RECORD_FORMAT_SP

</td>
<td>
Standard play

</td>
</tr>
<tr>
<td>
ED_RECORD_FORMAT_LP

</td>
<td>
Long play

</td>
</tr>
<tr>
<td>
ED_RECORD_FORMAT_EP

</td>
<td>
Extended play

</td>
</tr>
</table> 


#### - StepFrames

Indicates the frame step count.


#### - SetpField

Indicates the field step count.


#### - Preroll

Indicates the preroll amount.


#### - RecPreroll

Indicates the record preroll amount.


#### - Postroll

Indicates the postroll amount.


#### - EditDelay

Indicates the edit delay amount.


#### - PlayTCDelay

Indicates the play timecode delay amount.


#### - RecTCDelay

Indicates the record timecode delay amount.


#### - EditField

Indicates the edit field.


#### - FrameServo

Specifies the frame servo.


#### - ColorFrameServo

Specifies the color frame servo.


#### - ServoRef

Specifies the servo ref.
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
ED_REF_EXTERNAL

</td>
<td>
External

</td>
</tr>
<tr>
<td>
ED_REF_INPUT

</td>
<td>
Input

</td>
</tr>
<tr>
<td>
ED_REF_INTERNAL

</td>
<td>
Internal

</td>
</tr>
<tr>
<td>
ED_REF_AUTO

</td>
<td>
Auto

</td>
</tr>
</table> 


#### - WarnGenlock

Indicates the warn genlock.


#### - SetTracking

Specifies the tracking.
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
ED_TRACKING_PLUS

</td>
<td>
Plus

</td>
</tr>
<tr>
<td>
ED_TRACKING_MINUS

</td>
<td>
Minus

</td>
</tr>
<tr>
<td>
ED_TRACKING_RESET

</td>
<td>
Reset

</td>
</tr>
</table> 


#### - VolumeName

Specifies the volume name.


#### - Ballistic

Specifies any proprietary data.


#### - Speed

Specifies the speed.


#### - CounterFormat

Specifies the counter format.


#### - TunerChannel

Indicates the tuner channel.


#### - TunerNumber

Indicates the tuner number.


#### - TimerEvent

Specifies a timer event.


#### - TimerStartDay

Indicates the timer start-day.


#### - TimerStartTime

Indicates the timer start-time.


#### - TimerStopDay

Indicates the timer stop-day.


#### - TimerStopTime

Indicates the timer stop-time.


## -remarks


Any ED_<i>Xxx</i> tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.


