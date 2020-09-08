---
UID: NE:eventdetectoroemadapter.__MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0005
title: EVENTACTIONTYPE
author: windows-driver-content
description: Actions to take on a detection.
tech.root: audio
ms.assetid: d2da5ce0-d894-42d8-a538-bab7e9196384
ms.author: windowsdriverdev
ms.date: 02/26/2019
keywords: ["EVENTACTIONTYPE enumeration"]
ms.keywords: EVENTACTIONTYPE, EVENTACTIONTYPE,
req.header: eventdetectoroemadapter.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: EVENTACTIONTYPE
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - __MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0005
 - eventdetectoroemadapter/__MIDL___MIDL_itf_eventdetectoroemadapter_0000_0000_0005
 - EVENTACTIONTYPE
 - eventdetectoroemadapter/EVENTACTIONTYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - eventdetectoroemadapter.h
api_name:
 - EVENTACTIONTYPE
product:
 - Windows
---

# EVENTACTIONTYPE enumeration


## -description

Enumeration that defines actions to take on a detection.

## -enum-fields

### -field EVENTACTIONTYPE_Accept 

0 - Event detection should be processed by the OS

### -field EVENTACTIONTYPE_Reject 

1 - Event detection should be rejected by OS - data collection should occur

### -field EVENTACTIONTYPE_Error 

3 - Error occurred, failing HR expected in EVENTACTION return

## -remarks

This enumeration is the part of the Event Detector OEM interface to be used for hardware keyword spotters. For more information, see [Voice Activation](https://docs.microsoft.com/windows-hardware/drivers/audio/voice-activation).

## -see-also

- [eventdetectoroemadapter](../eventdetectoroemadapter/index.md)

- [Audio](../_audio/index.md)

