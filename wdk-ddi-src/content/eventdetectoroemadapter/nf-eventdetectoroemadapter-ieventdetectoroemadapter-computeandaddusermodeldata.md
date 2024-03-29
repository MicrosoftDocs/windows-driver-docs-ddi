---
UID: NF:eventdetectoroemadapter.IEventDetectorOemAdapter.ComputeAndAddUserModelData
title: IEventDetectorOemAdapter::ComputeAndAddUserModelData
description: Adds the user specific model data to an existing model data blob.
tech.root: audio
ms.date: 02/25/2019
keywords: ["IEventDetectorOemAdapter::ComputeAndAddUserModelData"]
ms.keywords: IEventDetectorOemAdapter::ComputeAndAddUserModelData, ComputeAndAddUserModelData, IEventDetectorOemAdapter.ComputeAndAddUserModelData, IEventDetectorOemAdapter::ComputeAndAddUserModelData, IEventDetectorOemAdapter.ComputeAndAddUserModelData
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
 - IEventDetectorOemAdapter::ComputeAndAddUserModelData
 - eventdetectoroemadapter/IEventDetectorOemAdapter::ComputeAndAddUserModelData
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - eventdetectoroemadapter.h
api_name:
 - IEventDetectorOemAdapter::ComputeAndAddUserModelData
---

# IEventDetectorOemAdapter::ComputeAndAddUserModelData


## -description

Adds the user specific model data to an existing model data blob.

## -parameters

### -param ModelData

\[*In*\] - Pointer to IStream bound to model data, updated by this call.

### -param EventSelector

\[*In*\] - The [DETECTIONEVENTELECTOR](ns-eventdetectoroemadapter-detectioneventselector.md) that uniquely identifies this model.

### -param EventEndBytePos

\[*In*\] - A pointer to an array byte positions of the end of the audio event in the corresponding UserRecording. A value of -1 indicates the position was unavailable.

### -param UserRecordings

\[*In*\] - Pointer to an array of pointers to the previously verified recordings of the user.

Note that non-standard use of cbSize in WAVEFORMATEX - it is the size of the following PCM data for the user recording.

### -param NumUserRecordings

\[*In*\] - Number of recordings.

## -returns

This method returns HRESULT. It returns S_OK if the function exit successfully. Otherwise it returns:

- E_POINTER- UserModelData pointer is null.
- E_INVALIDARG - the DETECTIONEVENTELECTOR contains an invalid id.
- HRESULT_FROM_WIN32(ERROR_GEN_FAILURE) = unable to complete the processing.

## -remarks

This function is the part of the Event Detector OEM interface to be used for hardware keyword spotters. For more information, see [Voice Activation](/windows-hardware/drivers/audio/voice-activation).

## -see-also

- [eventdetectoroemadapter](../eventdetectoroemadapter/index.md)

- [Audio](../_audio/index.md)

