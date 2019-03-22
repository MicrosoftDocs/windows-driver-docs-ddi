---
UID: NS:eventdetectoroemadapter.__MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0008
title: EVENTACTION
author: windows-driver-content
description: Structure used to provide detail from ParseDetectionResults.
tech.root: audio
ms.assetid: 399761eb-8c8e-47a8-b150-de42cde0e0aa
ms.author: windowsdriverdev
ms.date: 03/22/2019
ms.topic: struct
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
targetos: Windows
---

# EVENTACTION structure

## -description

Structure used to provide detail from ParseDetectionResults.

## -struct-fields

### -field EventdActionType

Actions to take on a detection. This is a value from the [EventActionType](ne-eventdetectoroemadapter-eventactiontype.md) enumeration.  ??? TBD
  
### -field EventActionContextType

The types of context associated with an action. This is a value from the [EventActionContextType](ne-eventdetectoroemadapter-eventactioncontexttype.md) enumeration. ??? TBD

### -field Confidence

The confidence level of the __________________________. ??? TBD

### -field Scale

The scale as defined in the [EVENTACTIONSCALE](ne-eventdetectoroemadapter-eventactionscale.md) enumeration. The scale defines the quality associated with a specific detection can be used for telemetry when no confidence is available or confidence is confusing to report. ??? TBD

### -field ErrorCode
 
An HRESULT error code from ParseDetectionResults.  ??? TBD

## -remarks

This structure is the part of the Event Detector OEM interface to be used for hardware keyword spotters. For more information, see [Voice Activation](https://docs.microsoft.com/windows-hardware/drivers/audio/voice-activation).

## -see-also

- [eventdetectoroemadapter](../eventdetectoroemadapter/index.md)

- [Audio](../_audio/index.md)