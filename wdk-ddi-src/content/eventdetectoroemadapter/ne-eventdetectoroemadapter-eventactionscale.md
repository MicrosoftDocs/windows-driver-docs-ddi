---
UID: NE:eventdetectoroemadapter.__MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0007
title: EVENTACTIONSCALE
description: Enumeration defining the quality associated with a specific detection.
tech.root: audio
ms.date: 03/22/2019
keywords: ["EVENTACTIONSCALE enumeration"]
ms.keywords: EVENTACTIONSCALE, EVENTACTIONSCALE,
req.header: eventdetectoroemadapter.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: EVENTACTIONSCALE
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - __MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0007
 - eventdetectoroemadapter/__MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0007
 - EVENTACTIONSCALE
 - eventdetectoroemadapter/EVENTACTIONSCALE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - eventdetectoroemadapter.h
api_name:
 - EVENTACTIONSCALE
product:
 - Windows
---

# EVENTACTIONSCALE enumeration


## -description

Enumeration defining the quality associated with a specific detection. It can be used for telemetry when no confidence is available or confidence is confusing to report.

## -enum-fields

### -field EVENTACTIONSCALE_High 

0 - High confidence

### -field EVENTACTIONSCALE_Medium 

1 - Medium confidence

### -field EVENTACTIONSCALE_Low 

2 - Low confidence

## -remarks

This enumeration is the part of the Event Detector OEM interface to be used for hardware keyword spotters. For more information, see [Voice Activation](/windows-hardware/drivers/audio/voice-activation).

## -see-also

- [eventdetectoroemadapter](../eventdetectoroemadapter/index.md)

- [Audio](../_audio/index.md)
