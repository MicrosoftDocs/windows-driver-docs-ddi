---
UID: NF:eventdetectoroemadapter.IEventDetectorOemAdapter.VerifyUserEventData
title: IEventDetectorOemAdapter::VerifyUserEventData
author: windows-driver-content
description: Verifies the user recording for the given EVENTID.
tech.root: audio
ms.assetid: 7f4bf4e4-d635-4738-9ce3-45d55eda52ac
ms.author: windowsdriverdev
ms.date: 02/25/2019
ms.topic: method
ms.keywords: IEventDetectorOemAdapter::VerifyUserEventData, VerifyUserEventData, IEventDetectorOemAdapter.VerifyUserEventData, IEventDetectorOemAdapter::VerifyUserEventData, IEventDetectorOemAdapter.VerifyUserEventData
req.header: eventdetectoroemadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl: eventdetectoroemadapter.idl
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- COM
api_location: 
- eventdetectoroemadapter.h
api_name: 
- IEventDetectorOemAdapter.VerifyUserEventData
product: 
- Windows
targetos: Windows
ms.custom: 19H1 
---

# IEventDetectorOemAdapter::VerifyUserEventData


## -description

Verifies the user recording for the given EVENTID.


## -parameters

### -param ModelData
\[*In*\] - ModelData- Pointer to IStream bound to model data for a given stored model (optional).

### -param UserRecording
\[*In*\] - Pointer to the buffer containing the raw data in the appropriate format. Note that non-standard use of cbSize in WAVEFORMATEX. It is the size of the following: (PCM data for the user recording).

### -param EventSelector
\[*In*\] - The [DETECTIONEVENTELECTOR](ns-eventdetectoroemadapter-detectioneventselector.md) associated with this UserRecording.

### -param EventEndBytePos
\[*In*\] - Byte position of the end of the sound pattern in the UserRecording. A value of -1 indicates the position was unavailable.


## -returns

It returns S_OK if the function exit successfully. Otherwise it returns:

- E_INVALIDARG- UserModelData pointer is null or Keyword Id or LangId are invalid
- E_NO_MATCH- The user recording didn't contain the keyword

Optional return values that may be implemented:

- E_VOICE_TOO_SOFT- User recording isn't loud enough
- E_VOICE_TOO_LOUD- User recording is too loud
- E_VOICE_TOO_SLOW- User was speaking too slowly for recognition
- E_VOICE_TOO_FAST- User was speaking too fast for recognition
- E_VOICE_PROCESSING_ERROR - An unrecoverable error occurred

## -remarks

This function is the part of the Event Detector OEM interface to be used for hardware keyword spotters. For more information, see [Voice Activation](https://docs.microsoft.com/windows-hardware/drivers/audio/voice-activation).



## -see-also

- [eventdetectoroemadapter](../eventdetectoroemadapter/index.md)

- [Audio](../_audio/index.md)