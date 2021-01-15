---
UID: NS:eventdetectoroemadapter.__MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0003
title: DETECTIONEVENT
description: Structure to specify uniquely supported detection events available.
tech.root: audio
ms.date: 04/11/2019
keywords: ["DETECTIONEVENT structure"]
ms.keywords: DETECTIONEVENT, DETECTIONEVENT,
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
req.typenames: DETECTIONEVENT
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - __MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0003
 - eventdetectoroemadapter/__MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0003
 - DETECTIONEVENT
 - eventdetectoroemadapter/DETECTIONEVENT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - eventdetectoroemadapter.h
api_name:
 - __MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0003
 - DETECTIONEVENT
product:
 - Windows
---

# DETECTIONEVENT structure


## -description

Structure to specify uniquely supported detection events available.

## -struct-fields

### -field EventId

A unique identifier for the keyword or audio event. This value is provided by Microsoft.

### -field EventFeat

 
The event features.

### -field ProviderId

The provider Id. This value is provided by Microsoft.

### -field DisplayName

 
The display name.

### -field UserModelValid

A boolean value indicating if the User Mode Model training is valid. FALSE if user model retraining is required for this event.

## -remarks

This structure is the part of the Event Detector OEM interface to be used for hardware keyword spotters. For more information, see [Voice Activation](/windows-hardware/drivers/audio/voice-activation).

## -see-also

- [eventdetectoroemadapter](../eventdetectoroemadapter/index.md)

- [Audio](../_audio/index.md)

