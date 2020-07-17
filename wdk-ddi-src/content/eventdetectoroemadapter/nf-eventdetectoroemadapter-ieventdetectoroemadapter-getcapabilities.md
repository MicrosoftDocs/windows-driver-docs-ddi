---
UID: NF:eventdetectoroemadapter.IEventDetectorOemAdapter.GetCapabilities
title: IEventDetectorOemAdapter::GetCapabilities
author: windows-driver-content
description: Returns langauges and detector features supported by the object.
tech.root: audio
ms.assetid: cd025bdc-7f10-4881-9620-b77570455c18
ms.author: windowsdriverdev
ms.date: 02/25/2019 
keywords: ["IEventDetectorOemAdapter::GetCapabilities"]
f1_keywords:
 - "eventdetectoroemadapter/IEventDetectorOemAdapter.GetCapabilities"
 - "IEventDetectorOemAdapter.GetCapabilities"
ms.keywords: IEventDetectorOemAdapter::GetCapabilities, GetCapabilities, IEventDetectorOemAdapter.GetCapabilities, IEventDetectorOemAdapter::GetCapabilities, IEventDetectorOemAdapter.GetCapabilities
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
- IEventDetectorOemAdapter.GetCapabilities
product: 
- Windows
targetos: Windows
ms.custom: 19H1 
---

# IEventDetectorOemAdapter::GetCapabilities


## -description
Returns langauges and detector features supported by the object.

## -parameters

### -param GlobalFeatureSupport

\[*Out*\] - Pointer to EVENTFEATURES indicating what features are supported.

### -param LangIds

\[*Out*\] - Pointer to an array of LANGIDs supported by the object.

### -param NumLanguages

\[*Out*\] - Pointer to the number of LANGIDs in the array.

### -param NumUserRecordings

\[*Out*\] - Pointer to the number of user recordings required for training.

### -param ppFormat

\[*Out*\] - Pointer to a pointer to the media type required by the object for user training and user customization.

## -returns
This method returns HRESULT. It returns S_OK if the function exit successfully. It can return E_POINTER if one of the out parameter pointers is NULL.

## -remarks

This function is the part of the Event Detector OEM interface to be used for hardware keyword spotters. For more information, see [Voice Activation](https://docs.microsoft.com/windows-hardware/drivers/audio/voice-activation).

## -see-also

- [eventdetectoroemadapter](../eventdetectoroemadapter/index.md)

- [Audio](../_audio/index.md)
