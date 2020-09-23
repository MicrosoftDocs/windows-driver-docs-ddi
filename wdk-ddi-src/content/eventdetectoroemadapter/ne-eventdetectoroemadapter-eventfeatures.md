---
UID: NE:eventdetectoroemadapter.__MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0002
title: EVENTFEATURES
description: Event features.
tech.root: audio
ms.assetid: 706fbd00-b95e-4b4d-9059-215a3f01648a
ms.date: 04/10/2019
keywords: ["EVENTFEATURES enumeration"]
ms.keywords: EVENTFEATURES, EVENTFEATURES,
req.header: eventdetectoroemadapter.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: EVENTFEATURES
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - __MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0002
 - eventdetectoroemadapter/__MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0002
 - EVENTFEATURES
 - eventdetectoroemadapter/EVENTFEATURES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - eventdetectoroemadapter.h
api_name:
 - EVENTFEATURES
product:
 - Windows
---

# EVENTFEATURES enumeration


## -description

Enumeration that defines event features.

## -enum-fields

### -field EVENTFEATURES_NoEventFeatures

0x0 - No event features.

### -field EVENTFEATURES_SupportsUserTraining 

0x1 - SpeakerID support.

### -field EVENTFEATURES_SupportUserCustomization 

0x2 - User defined keyword.

### -field EVENTFEATURES_ArmPatternRequiresArmState 

0x4 - Is active arm state required for BuildArmingPatternData (Global only feature).

### -field EVENTFEATURES_

0x8 - Does detector support a single language for all keywords.

## -remarks

This enumeration is the part of the Event Detector OEM interface to be used for hardware keyword spotters. For more information, see [Voice Activation](/windows-hardware/drivers/audio/voice-activation).

## -see-also

- [eventdetectoroemadapter](../eventdetectoroemadapter/index.md)

- [Audio](../_audio/index.md)