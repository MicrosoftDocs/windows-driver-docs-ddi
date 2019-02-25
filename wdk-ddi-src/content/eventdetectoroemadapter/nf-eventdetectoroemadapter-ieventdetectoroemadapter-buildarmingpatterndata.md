---
UID: NF:eventdetectoroemadapter.IEventDetectorOemAdapter.BuildArmingPatternData
title: IEventDetectorOemAdapter::BuildArmingPatternData
author: windows-driver-content
description: Builds the pattern data to be used on a subsequent arm request - this is done once for each pin instance.
tech.root: audio
ms.assetid: 441cfb5c-8365-4260-b12f-285df29d54f5
ms.author: windowsdriverdev
ms.date: 02/25/2019 
ms.topic: method
ms.keywords: IEventDetectorOemAdapter::BuildArmingPatternData, BuildArmingPatternData, IEventDetectorOemAdapter.BuildArmingPatternData, IEventDetectorOemAdapter::BuildArmingPatternData, IEventDetectorOemAdapter.BuildArmingPatternData
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
req.idl:
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
- IEventDetectorOemAdapter.BuildArmingPatternData
product: 
- Windows
targetos: Windows

---

# IEventDetectorOemAdapter::BuildArmingPatternData


## -description

Builds the pattern data to be used on a subsequent arm request - this is done once for each pin instance.
The GUID in the SOUNDDETECTOR_PATTERNHEADER can be used to provide additional context to allow optional model use but the expectation is that the individual DETECTIONEVENTS can be armed and disarmed given appropriate feature support.

## -parameters

### -param UserModelData
*Input*

Pointer to IStream bound to model data (optional).

### -param EventSelectors
*Input*

Pointer to the array of [DETECTIONEVENTSELECTOR](ns-eventdetectoroemadapter-detectioneventselector) structs to be detected - associated with this BurstID.

### -param NumEventSelectors
*Input*

NumEventSelectors - Number of [DETECTIONEVENTSELECTOR](ns-eventdetectoroemadapter-detectioneventselector) structs passed.

### -param PatternData

*Output*

Pattern data created to reflect the input eventlanguageuser sets for an arm.


## -returns

This method returns HRESULT. It returns S_OK if the function exit successfully. Otherwise it returns E_INVALIDARG - UserModelData pointer is null or one or more of the DETECTIONEVENTELECTOR contains invalid ids.

HRESULT_FROM_WIN32(ERROR_GEN_FAILURE) = unable to complete the processing.

## -remarks

This function is the part of the Event Detector OEM interface to be used for hardware keyword spotters. For more information, see [Voice Activation](https://docs.microsoft.com/windows-hardware/drivers/audio/voice-activation).

## -see-also

- [eventdetectoroemadapter](../eventdetectoroemadapter/index.md)

- [Audio](../_audio/index.md)
