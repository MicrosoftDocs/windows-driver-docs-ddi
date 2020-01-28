---
UID: NS:eventdetectoroemadapter.__MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0004
title: DETECTIONEVENTSELECTOR
author: windows-driver-content
description: A structure to reference a specific detection event.
tech.root: audio
ms.assetid: d29d2e29-74e2-44bb-a296-ecefc25437d5
ms.author: windowsdriverdev
ms.date: 02/25/2019
f1_keywords:
 - "eventdetectoroemadapter/DETECTIONEVENTSELECTOR"
ms.keywords: DETECTIONEVENTSELECTOR, DETECTIONEVENTSELECTOR, 
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
req.typenames: DETECTIONEVENTSELECTOR
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - eventdetectoroemadapter.h
api_name: 
 - DETECTIONEVENTSELECTOR
product: 
 - Windows
targetos: Windows
ms.custom: 19H1 
---

# DETECTIONEVENTSELECTOR structure

## -description

A structure to reference a specific detection event.


## -struct-fields

### -field Event

A [DETECTIONEVENT](ns-eventdetectoroemadapter-detectionevent.md) event.

### -field LangId

The language ID. 
 
### -field UserId

Specifies the User. 0 if no user indicated.
 
### -field Armed

A BOOL that specifies if the keyword is currently armed.
 

## -remarks

This structure is the part of the Event Detector OEM interface to be used for hardware keyword spotters. For more information, see [Voice Activation](https://docs.microsoft.com/windows-hardware/drivers/audio/voice-activation).

## -see-also

- [eventdetectoroemadapter](../eventdetectoroemadapter/index.md)

- [Audio](../_audio/index.md)
