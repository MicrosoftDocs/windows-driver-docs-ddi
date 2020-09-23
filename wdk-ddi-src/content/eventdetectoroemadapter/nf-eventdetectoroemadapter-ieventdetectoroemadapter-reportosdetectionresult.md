---
UID: NF:eventdetectoroemadapter.IEventDetectorOemAdapter.ReportOSDetectionResult
title: IEventDetectorOemAdapter::ReportOSDetectionResult
author: windows-driver-content
description: Called to provide second stage result to OEM dll.
tech.root: audio
ms.assetid: b2cb4413-7893-4d8b-aeb2-01698e95dcf5
ms.author: windowsdriverdev
ms.date: 02/25/2019
keywords: ["IEventDetectorOemAdapter::ReportOSDetectionResult"]
ms.keywords: IEventDetectorOemAdapter::ReportOSDetectionResult, ReportOSDetectionResult, IEventDetectorOemAdapter.ReportOSDetectionResult, IEventDetectorOemAdapter::ReportOSDetectionResult, IEventDetectorOemAdapter.ReportOSDetectionResult
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
req.idl: eventdetectoroemadapter.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - IEventDetectorOemAdapter::ReportOSDetectionResult
 - eventdetectoroemadapter/IEventDetectorOemAdapter::ReportOSDetectionResult
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - eventdetectoroemadapter.h
api_name:
 - IEventDetectorOemAdapter.ReportOSDetectionResult
product:
 - Windows
---

# IEventDetectorOemAdapter::ReportOSDetectionResult


## -description

Called to provide second stage result to OEM dll.

## -parameters

### -param EventSelector

\[*In*\] - Pointer to IStream bound to model data for the arming pattern (Optional).

### -param EventAction

\[*In*\] - Pointer to the [SOUNDDETECTOR_PATTERNHEADER](ns-eventdetectoroemadapter-sounddetector_patternheader.md) from the DDI.

## -returns

This method returns HRESULT. It returns S_OK if the function exit successfully.

## -remarks

This function is the part of the Event Detector OEM interface to be used for hardware keyword spotters. For more information, see [Voice Activation](/windows-hardware/drivers/audio/voice-activation).

## -see-also

- [eventdetectoroemadapter](../eventdetectoroemadapter/index.md)

- [Audio](../_audio/index.md)