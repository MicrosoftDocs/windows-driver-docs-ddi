---
UID: NS:eventdetectoroemadapter.__MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0008
title: EVENTACTION
author: windows-driver-content
description: Structure used to provide detail from ParseDetectionResults.
tech.root: audio
ms.assetid: 399761eb-8c8e-47a8-b150-de42cde0e0aa
ms.author: windowsdriverdev
ms.date: 04/10/2019
keywords: ["EVENTACTION structure"]
ms.keywords: EVENTACTION, EVENTACTION,
req.header: eventdetectoroemadapter.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: EVENTACTION
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - __MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0008
 - eventdetectoroemadapter/__MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0008
 - EVENTACTION
 - eventdetectoroemadapter/EVENTACTION
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - eventdetectoroemadapter.h
api_name:
 - EVENTACTION
product:
 - Windows
---

# EVENTACTION structure


## -description

Structure used to provide detail from ParseDetectionResults.

## -struct-fields

### -field EventdActionType

Actions to take on a detection. This is a value from the [EventActionType](ne-eventdetectoroemadapter-eventactiontype.md) enumeration.

### -field EventActionContextType

The types of context associated with an action. This is a value from the [EventActionContextType](ne-eventdetectoroemadapter-eventactioncontexttype.md) enumeration.

### -field Confidence

The confidence level is a number between 0.0 and 1.0 that represents how confident the algorithm is that the keyword was detected.

### -field Scale

The scale as defined in the [EVENTACTIONSCALE](ne-eventdetectoroemadapter-eventactionscale.md) enumeration. The scale defines the quality associated with a specific detection can be used for telemetry when no confidence is available or confidence is confusing to report.

### -field ErrorCode

 
An HRESULT error code from ParseDetectionResults.

## -remarks

This structure is the part of the Event Detector OEM interface to be used for hardware keyword spotters. For more information, see [Voice Activation](/windows-hardware/drivers/audio/voice-activation).

## -see-also

- [eventdetectoroemadapter](../eventdetectoroemadapter/index.md)

- [Audio](../_audio/index.md)