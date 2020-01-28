---
UID: NF:strmini.StreamClassScheduleTimer
title: StreamClassScheduleTimer function (strmini.h)
description: The minidriver calls the StreamClassScheduleTimer routine to schedule a timer, and to specify a routine that is called when the timer expires.
old-location: stream\streamclassscheduletimer.htm
tech.root: stream
ms.assetid: 83271c19-911b-481a-bc25-c0b3816cf800
ms.date: 04/23/2018
ms.keywords: StreamClassScheduleTimer, StreamClassScheduleTimer routine [Streaming Media Devices], strclass-routines_73f92fc4-e9bf-40af-8dff-9c2e740dba20.xml, stream.streamclassscheduletimer, strmini/StreamClassScheduleTimer
f1_keywords:
 - "strmini/StreamClassScheduleTimer"
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

The minidriver calls the **StreamClassScheduleTimer** routine to schedule a timer, and to specify a routine that is called when the timer expires.

## -parameters

### -param StreamObject [in, optional]

Specifies the stream that sets the timer, or **NULL** if the timer is set for the whole driver. The minidriver may only schedule one timer per stream, and one for the driver as a whole. This parameter is optional.

### -param HwDeviceExtension [in]

Pointer to the minidriver's device extension. The minidriver specifies the size of this buffer in the [HW_INITIALIZATION_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data) structure it passes when it registers itself via [StreamClassRegisterMinidriver](https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassregisteradapter). The class driver then passes pointers to the buffer in the **HwDeviceExtension** member of the [HW_STREAM_REQUEST_BLOCK](https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_request_block), [HW_STREAM_OBJECT](https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_object), [HW_TIME_CONTEXT](https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_time_context), and [PORT_CONFIGURATION_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_port_configuration_information) structures it passes to the minidriver.

### -param NumberOfMicroseconds [in]

Specifies the amount of time, in microseconds, before the timer expires.

### -param TimerRoutine [in]

Specifies the routine called when the timer expires. The routine's prototype must be of the form:

```cpp
TimerRoutine(PVOID Context);
```

### -param Context [in]

Pointer to a context that the class driver passes to the callback routine once the timer expires.

## -returns

None
