---
UID: NF:strmini.StreamClassCallAtNewPriority
title: StreamClassCallAtNewPriority function (strmini.h)
description: The StreamClassCallAtNewPriority routine schedules a routine to be called at a different priority.
tech.root: stream
ms.date: 03/03/2023
keywords: ["StreamClassCallAtNewPriority function"]
ms.keywords: StreamClassCallAtNewPriority, StreamClassCallAtNewPriority routine [Streaming Media Devices], strclass-routines_6335ceee-08a1-4078-a9ce-aaa15d8158cd.xml, stream.streamclasscallatnewpriority, strmini/StreamClassCallAtNewPriority
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
req.irql: (See Parameters section)
targetos: Windows
req.typenames: 
f1_keywords:
 - StreamClassCallAtNewPriority
 - strmini/StreamClassCallAtNewPriority
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Stream.lib
 - Stream.dll
api_name:
 - StreamClassCallAtNewPriority
---

## -description

The **StreamClassCallAtNewPriority** routine schedules a routine to be called at a different priority.

## -parameters

### -param StreamObject [in, optional]

Pointer to an HW_STREAM_OBJECT structure specifying the stream is associated with the routine, or **NULL** if the routine is associated with the device as a whole. There can be only one routine per stream, and only one routine for the device. This parameter is optional.

### -param HwDeviceExtension [in]

Pointer to the minidriver's device extension. The minidriver specifies the size of this buffer in the [HW_INITIALIZATION_DATA](/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data) structure it passes when it registers itself via [StreamClassRegisterMinidriver](/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassregisteradapter). The class driver then passes pointers to the buffer in the **HwDeviceExtension** member of the [HW_STREAM_REQUEST_BLOCK](/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_request_block), [HW_STREAM_OBJECT](/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_object), [HW_TIME_CONTEXT](/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_time_context), and [PORT_CONFIGURATION_INFORMATION](/windows-hardware/drivers/ddi/strmini/ns-strmini-_port_configuration_information) structures it passes to the minidriver.

### -param Priority [in]

Specifies one of the values listed in the following table.

| Priority | Usage |
|---|---|
| High | The stream class driver calls the routine at the same priority as the minidriver's **StrMini***Xxx* callbacks. Do not use this setting unless the routine must be synchronized with the minidriver's interrupt service routine. |
| Dispatch | The stream class driver calls the routine at DISPATCH_LEVEL. Use this priority if the routine takes less than 1 millisecond to complete. |
| Low | The stream class driver calls the routine at PASSIVE_LEVEL. Use this priority if the routine takes less than 1 millisecond to complete. |
| LowToHigh | Used to allow a thread called at low priority to return to high priority so that other stream class driver services can be called. |

### -param PriorityRoutine [in]

Pointer to a minidriver-supplied [StrMiniPriorityRoutine](/windows-hardware/drivers/ddi/strmini/nc-strmini-phw_priority_routine) to be called at the specified priority level.

### -param Context [in]

Specifies the parameter to be passed to the *PriorityRoutine*.

## -returns

None
