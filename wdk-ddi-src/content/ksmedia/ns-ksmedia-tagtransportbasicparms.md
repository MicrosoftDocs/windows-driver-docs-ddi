---
UID: NS:ksmedia.tagTRANSPORTBASICPARMS
title: tagTRANSPORTBASICPARMS
author: windows-driver-content
description: The TRANSPORTBASICPARMS structure is defined but not used.
old-location: stream\transportbasicparms.htm
old-project: stream
ms.assetid: 40e305b3-e91c-4227-99e7-dbb939082f54
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: TRANSPORTBASICPARMS, PTRANSPORTBASICPARMS, stream.transportbasicparms, *PTRANSPORTBASICPARMS, tagTRANSPORTBASICPARMS, ksmedia/TRANSPORTBASICPARMS, TRANSPORTBASICPARMS structure [Streaming Media Devices], ksmedia/PTRANSPORTBASICPARMS, PTRANSPORTBASICPARMS structure pointer [Streaming Media Devices], vidcapstruct_5a5cdf6a-56f3-43ad-9bab-e5d406052707.xml
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
req.typenames: TRANSPORTBASICPARMS, *PTRANSPORTBASICPARMS
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




### -field TimeFormat

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
 


### -field TimeReference

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
 


### -field Superimpose

Indicates whether to enable or disable the onscreen display. Specify <b>TRUE</b> to enable, <b>FALSE</b> to disable.


### -field EndStopAction

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
 


### -field RecordFormat

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
 


### -field StepFrames

Indicates the frame step count.


### -field SetpField

Indicates the field step count.


### -field Preroll

Indicates the preroll amount.


### -field RecPreroll

Indicates the record preroll amount.


### -field Postroll

Indicates the postroll amount.


### -field EditDelay

Indicates the edit delay amount.


### -field PlayTCDelay

Indicates the play timecode delay amount.


### -field RecTCDelay

Indicates the record timecode delay amount.


### -field EditField

Indicates the edit field.


### -field FrameServo

Specifies the frame servo.


### -field ColorFrameServo

Specifies the color frame servo.


### -field ServoRef

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
 


### -field WarnGenlock

Indicates the warn genlock.


### -field SetTracking

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
 


### -field VolumeName

Specifies the volume name.


### -field Ballistic

Specifies any proprietary data.


### -field Speed

Specifies the speed.


### -field CounterFormat

Specifies the counter format.


### -field TunerChannel

Indicates the tuner channel.


### -field TunerNumber

Indicates the tuner number.


### -field TimerEvent

Specifies a timer event.


### -field TimerStartDay

Indicates the timer start-day.


### -field TimerStartTime

Indicates the timer start-time.


### -field TimerStopDay

Indicates the timer stop-day.


### -field TimerStopTime

Indicates the timer stop-time.


## -remarks



Any ED_<i>Xxx</i> tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.



