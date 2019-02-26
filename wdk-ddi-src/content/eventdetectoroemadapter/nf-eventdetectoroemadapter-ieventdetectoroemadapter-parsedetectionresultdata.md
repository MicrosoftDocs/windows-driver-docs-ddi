---
UID: NF:eventdetectoroemadapter.IEventDetectorOemAdapter.ParseDetectionResultData
title: IEventDetectorOemAdapter::ParseDetectionResultData
author: windows-driver-content
description: Uses the input model data and SOUNDDETECTOR_PATTERNHEADER to determine the DETECTIONEVENTID,LANGID and USER detected. 
tech.root: audio
ms.assetid: 862be70a-9d24-442f-a4fa-deb3fbefd4c6
ms.author: windowsdriverdev
ms.date: 02/26/2019
ms.topic: method
ms.keywords: IEventDetectorOemAdapter::ParseDetectionResultData, ParseDetectionResultData, IEventDetectorOemAdapter.ParseDetectionResultData, IEventDetectorOemAdapter::ParseDetectionResultData, IEventDetectorOemAdapter.ParseDetectionResultData
req.header: eventdetectoroemadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- COM
api_location: 
- eventdetectoroemadapter.h
api_name: 
- IEventDetectorOemAdapter.ParseDetectionResultData
product: 
- Windows
targetos: Windows

---

# IEventDetectorOemAdapter::ParseDetectionResultData


## -description

Uses the input model data and [SOUNDDETECTOR_PATTERNHEADER](ns-eventdetectoroemadapter-sounddetector_patternheader.md) to determine the DETECTIONEVENTID,LANGID and USER detected.

## -parameters

### -param UserModelData
\[*In*\] - Pointer to IStream bound to model data for the arming pattern (Optional).

### -param Result
\[*In*\] - Pointer to the [SOUNDDETECTOR_PATTERNHEADER](ns-eventdetectoroemadapter-sounddetector_patternheader.md) from DDI.

### -param AssistantContext
\[*In*\] - AssistantContext - Data to be provided to the assistant.

### -param EventSelector
\[*Out*\] - The DETECTIONEVENTELECTOR associated with this detection.

### -param EventAction
\[*Out*\] - Action for the system to take, along with associated context.

### -param EventStartPerformanceCounterValue
\[*Out*\] - Event start time, if available, else zero.

### -param EventEndPerformanceCounterValue
\[*Out*\] - Event end time, if available, else zero.

### -param DebugOutput
\[*Out*\] - Optional string to provide open detail, used for logging and telemetry.

## -returns

Returns S_OK if the function exit successfully. Otherwise it returns:

- E_INVALIDARG - If called inconsistently w.r.t. the model data and its header.
- E_POINTER - One or more of the out parameter pointers is null.
- HRESULT_FROM_WIN32(ERROR_GEN_FAILURE) = unable to complete the processing.

## -remarks

This function is the part of the Event Detector OEM interface to be used for hardware keyword spotters. For more information, see [Voice Activation](https://docs.microsoft.com/windows-hardware/drivers/audio/voice-activation).

## -see-also

- [eventdetectoroemadapter](../eventdetectoroemadapter/index.md)

- [Audio](../_audio/index.md)