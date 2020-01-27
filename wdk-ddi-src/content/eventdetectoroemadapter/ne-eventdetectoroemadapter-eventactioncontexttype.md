---
UID: NE:eventdetectoroemadapter.__MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0006
title: EVENTACTIONCONTEXTTYPE
author: windows-driver-content
description: Enumeration the types of context associated with an action.
tech.root: audio
ms.assetid: 5d763702-145b-40e9-9f34-8c7137d7e6cc
ms.author: windowsdriverdev
ms.date: 02/25/2019
f1_keywords:
 - "eventdetectoroemadapter/EVENTACTIONCONTEXTTYPE"
ms.keywords: EVENTACTIONCONTEXTTYPE, EVENTACTIONCONTEXTTYPE, 
req.header: eventdetectoroemadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: EVENTACTIONCONTEXTTYPE
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - eventdetectoroemadapter.h
api_name: 
 - EVENTACTIONCONTEXTTYPE
product: 
 - Windows
targetos: Windows
ms.custom: 19H1 
---

# EVENTACTIONCONTEXTTYPE enumeration

## -description

Enumeration the types of context associated with an action.

## -enum-fields

### -field EVENTACTIONCONTEXTTYPE_None 
0 - no additional conxt provided

### -field EVENTACTIONCONTEXTTYPE_Confidence 
1 - Value between 0.0 and 1.0

### -field EVENTACTIONCONTEXTTYPE_Scale 
2  - High, Medium, Low

### -field EVENTACTIONCONTEXTTYPE_ErrorCode 
3 - OEM defined

## -remarks

This enumeration is the part of the Event Detector OEM interface to be used for hardware keyword spotters. For more information, see [Voice Activation](https://docs.microsoft.com/windows-hardware/drivers/audio/voice-activation).

## -see-also

- [eventdetectoroemadapter](../eventdetectoroemadapter/index.md)

- [Audio](../_audio/index.md)
