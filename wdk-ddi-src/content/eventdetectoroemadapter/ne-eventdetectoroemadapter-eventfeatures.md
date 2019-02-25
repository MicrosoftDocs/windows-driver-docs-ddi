---
UID: NE:eventdetectoroemadapter.__MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0002
title: EVENTFEATURES
author: windows-driver-content
description: Event features.
tech.root: audio
ms.assetid: 706fbd00-b95e-4b4d-9059-215a3f01648a
ms.author: windowsdriverdev
ms.date: 02/22/2019
ms.topic: enum
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
targetos: Windows
---

# EVENTFEATURES enumeration

## -description

Event features.


## -enum-fields

### -field EVENTFEATURES_NoEventFeatures
0x0 - No event features.

### -field EVENTFEATURES_SupportsUserTraining 
0x1 - SpeakerID support.

### -field EVENTFEATURES_SupportUserCustomization 
0x2 - User defined keyword.

### -field EVENTFEATURES_ArmPatternRequiresArmState 
 0x4 - Is active arm state required for BuildArmingPatternData (Global only feature).


## -remarks

## -see-also

- [eventdetectoroemadapter](../eventdetectoroemadapter/index.md)

- [Audio](../_audio/index.md)
