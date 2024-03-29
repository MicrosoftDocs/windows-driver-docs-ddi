---
UID: NF:eventdetectoroemadapter.IEventDetectorOemAdapter.GetCapabilitiesForLanguage
title: IEventDetectorOemAdapter::GetCapabilitiesForLanguage
description: Returns the events supported by the specific language.
tech.root: audio
ms.date: 02/25/2019
keywords: ["IEventDetectorOemAdapter::GetCapabilitiesForLanguage"]
ms.keywords: IEventDetectorOemAdapter::GetCapabilitiesForLanguage, GetCapabilitiesForLanguage, IEventDetectorOemAdapter.GetCapabilitiesForLanguage, IEventDetectorOemAdapter::GetCapabilitiesForLanguage, IEventDetectorOemAdapter.GetCapabilitiesForLanguage
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
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - IEventDetectorOemAdapter::GetCapabilitiesForLanguage
 - eventdetectoroemadapter/IEventDetectorOemAdapter::GetCapabilitiesForLanguage
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - eventdetectoroemadapter.h
api_name:
 - IEventDetectorOemAdapter::GetCapabilitiesForLanguage
---

# IEventDetectorOemAdapter::GetCapabilitiesForLanguage


## -description

Returns the events supported by the specific language.

## -parameters

### -param LangId

\[*In*\] - Language ID for this displayspeech language for example, 0x0409 is used for English (United States). Language changes should be viewed as re-initialization.

### -param EventIds

\[*Out*\] - Pointer to an array of [DETECTIONEVENT](ns-eventdetectoroemadapter-detectionevent.md) structures supported by this detector.

### -param NumEvents

\[*Out*\] - Pointer to the number of [DETECTIONEVENT](ns-eventdetectoroemadapter-detectionevent.md) structures in the array.

## -returns

This method returns HRESULT. It returns S_OK if the function exit successfully. It can return E_POINTER if one of the out parameter pointers is NULL.

## -remarks

This function is the part of the Event Detector OEM interface to be used for hardware keyword spotters. For more information, see [Voice Activation](/windows-hardware/drivers/audio/voice-activation).

## -see-also

- [eventdetectoroemadapter](../eventdetectoroemadapter/index.md)

- [Audio](../_audio/index.md)

