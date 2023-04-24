---
UID: NS:ksmedia.tagTRANSPORTBASICPARMS
title: TRANSPORTBASICPARMS (ksmedia.h)
description: The TRANSPORTBASICPARMS structure is defined but not used.
tech.root: stream
ms.date: 03/15/2023
keywords: ["tagTRANSPORTBASICPARMS structure"]
ms.keywords: "*PTRANSPORTBASICPARMS, PTRANSPORTBASICPARMS, PTRANSPORTBASICPARMS structure pointer [Streaming Media Devices], TRANSPORTBASICPARMS, TRANSPORTBASICPARMS structure [Streaming Media Devices], ksmedia/PTRANSPORTBASICPARMS, ksmedia/TRANSPORTBASICPARMS, stream.transportbasicparms, tagTRANSPORTBASICPARMS, vidcapstruct_5a5cdf6a-56f3-43ad-9bab-e5d406052707.xml"
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
targetos: Windows
req.typenames: TRANSPORTBASICPARMS, *PTRANSPORTBASICPARMS
f1_keywords:
 - tagTRANSPORTBASICPARMS
 - ksmedia/tagTRANSPORTBASICPARMS
 - PTRANSPORTBASICPARMS
 - ksmedia/PTRANSPORTBASICPARMS
 - TRANSPORTBASICPARMS
 - ksmedia/TRANSPORTBASICPARMS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - tagTRANSPORTBASICPARMS
 - PTRANSPORTBASICPARMS
 - TRANSPORTBASICPARMS
---

## -description

The TRANSPORTBASICPARMS structure is defined but not used.

## -struct-fields

### -field TimeFormat

Indicates the basic time format.

| Flag | Meaning |
|---|---|
| ED_FORMAT_MILLISECONDS | Milliseconds |
| ED_FORMAT_FRAMES | Frames |
| ED_FORMAT_REFERENCE_TIME | Reference time |
| ED_FORMAT_HMSF | Binary coded decimal, representing hours, minutes, seconds, and frames |
| ED_FORMAT_TMSF | Binary coded decimal, representing tracks, minutes, seconds, and frames |

### -field TimeReference

Indicates the basic time reference.

| Flag | Meaning |
|---|---|
| ED_TIMEREF_TIMECODE | Time code |
| ED_TIMEREF_CONTROL_TRACK | Control track |
| ED_TIMEREF_INDEX | Index |

### -field Superimpose

Indicates whether to enable or disable the onscreen display. Specify **TRUE** to enable, **FALSE** to disable.

### -field EndStopAction

Specifies the stop action.

| Flag | Meaning |
|---|---|
| ED_MODE_STOP | Stop |
| ED_MODE_REWIND | Rewind |
| ED_MODE_FREEZE | Freeze/pause |

### -field RecordFormat

Indicates the basic record format.

| Flag | Meaning |
|---|---|
| ED_RECORD_FORMAT_SP | Standard play |
| ED_RECORD_FORMAT_LP | Long play |
| ED_RECORD_FORMAT_EP | Extended play |

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

| Flag | Meaning |
|---|---|
| ED_REF_EXTERNAL | External |
| ED_REF_INPUT | Input |
| ED_REF_INTERNAL | Internal |
| ED_REF_AUTO | Auto |

### -field WarnGenlock

Indicates the warn genlock.

### -field SetTracking

Specifies the tracking.

| Flag | Meaning |
|---|---|
| ED_TRACKING_PLUS | Plus |
| ED_TRACKING_MINUS | Minus |
| ED_TRACKING_RESET | Reset |

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

Any ED_*Xxx* tokens are defined in *xprtdefs.h* in the Microsoft DirectX SDK.
