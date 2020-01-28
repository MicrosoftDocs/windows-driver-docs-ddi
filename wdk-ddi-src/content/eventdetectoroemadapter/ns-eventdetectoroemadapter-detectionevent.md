---
UID: NS:eventdetectoroemadapter.__MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0003
title: DETECTIONEVENT
author: windows-driver-content
description: Structure to specify uniquely supported detection events available.
tech.root: audio
ms.assetid: 6c9e3e30-1598-4537-bc76-da5ffc552de3
ms.author: windowsdriverdev
ms.date: 04/11/2019
f1_keywords:
 - "eventdetectoroemadapter/DETECTIONEVENT"
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
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - eventdetectoroemadapter.h
api_name: 
 - DETECTIONEVENT
product: 
 - Windows
targetos: Windows
ms.custom: 19H1 
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

This structure is the part of the Event Detector OEM interface to be used for hardware keyword spotters. For more information, see [Voice Activation](https://docs.microsoft.com/windows-hardware/drivers/audio/voice-activation).

## -see-also

- [eventdetectoroemadapter](../eventdetectoroemadapter/index.md)

- [Audio](../_audio/index.md)
