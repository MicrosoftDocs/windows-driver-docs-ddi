---
UID: NE:eventdetectoroemadapter.__MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0007
title: EVENTACTIONSCALE
author: windows-driver-content
description: Enumeration defining the quality associated with a specific detection. 
tech.root: audio
ms.assetid: 27155e81-f33f-4342-9847-c5f4326c72fe
ms.author: windowsdriverdev
ms.date: 03/22/2019
keywords: ["EVENTACTIONSCALE enumeration"]
f1_keywords:
 - "eventdetectoroemadapter/EVENTACTIONSCALE"
 - "EVENTACTIONSCALE"
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
targetos: Windows
ms.custom: 19H1 
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

This enumeration is the part of the Event Detector OEM interface to be used for hardware keyword spotters. For more information, see [Voice Activation](https://docs.microsoft.com/windows-hardware/drivers/audio/voice-activation).

## -see-also

- [eventdetectoroemadapter](../eventdetectoroemadapter/index.md)

- [Audio](../_audio/index.md)
