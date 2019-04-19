---
UID: NS:eventdetectoroemadapter.IEventDetectorOemAdapterVtbl
title: IEventDetectorOemAdapterVtbl
author: windows-driver-content
description: IEventDetectorOemAdapterVtbl structure is an artifact created by the IDL. It is reserved for Microsoft use.
tech.root: audio
ms.assetid: 15246179-b019-440a-8984-efae4370e341
ms.author: windowsdriverdev
ms.date: 04/05/2019
ms.topic: struct
ms.keywords: IEventDetectorOemAdapterVtbl, IEventDetectorOemAdapterVtbl, 
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
req.typenames: IEventDetectorOemAdapterVtbl
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - eventdetectoroemadapter.h
api_name: 
 - IEventDetectorOemAdapterVtbl
product: 
 - Windows
targetos: Windows
ms.custom: 19H1 
---

# IEventDetectorOemAdapterVtbl structure

## -description

IEventDetectorOemAdapterVtbl structure is an artifact created by the IDL. It is reserved for Microsoft use.

## -struct-fields

### -field b
 
Reserved for Microsoft use.

### -field QueryInterface

Standard COM QueryInterface method.
 
### -field AddRef

Standard COM AddRef method.
 
### -field Release

Standard COM Release method.
 
### -field GetCapabilities

Returns langauges and detector features supported by the object. For more information, see [IEventDetectorOemAdapter::GetCapabilities method](nf-eventdetectoroemadapter-ieventdetectoroemadapter-getcapabilities.md).
 
### -field GetCapabilitiesForLanguage

Returns the events supported by the specific language. For more information, see [IEventDetectorOemAdapter::GetCapabilitiesForLanguage method](nf-eventdetectoroemadapter-ieventdetectoroemadapter-getcapabilitiesforlanguage.md).
 
### -field VerifyUserEventData

Verifies the user recording for the given EVENTID. For more information, see [IEventDetectorOemAdapter::VerifyUserEventData method](nf-eventdetectoroemadapter-ieventdetectoroemadapter-verifyusereventdata.md).
 
### -field ComputeAndAddUserModelData

Adds the user specific model data to an existing model data blob. For more information, see [IEventDetectorOemAdapter::ComputeAndAddUserModelData method](nf-eventdetectoroemadapter-ieventdetectoroemadapter-computeandaddusermodeldata.md).
 
### -field BuildArmingPatternData
Builds the pattern data to be used on a subsequent arm request - this is done once for each pin instance. For more information, see [IEventDetectorOemAdapter::BuildArmingPatternData method](nf-eventdetectoroemadapter-ieventdetectoroemadapter-buildarmingpatterndata.md).
 
### -field ParseDetectionResultData
Uses the input model data and SOUNDDETECTOR_PATTERNHEADER to determine the DETECTIONEVENTID,LANGID and USER detected.
For more information, see [IEventDetectorOemAdapter::ParseDetectionResultData method](nf-eventdetectoroemadapter-ieventdetectoroemadapter-parsedetectionresultdata.md).
 
### -field ReportOSDetectionResult
Called to provide second stage result to OEM dll. For more information, see [IEventDetectorOemAdapter::ReportOSDetectionResult method](nf-eventdetectoroemadapter-ieventdetectoroemadapter-reportosdetectionresult.md).


## -remarks

This structure is an artifact created by the IDL. It is reserved for Microsoft use.


## -see-also

- [eventdetectoroemadapter](../eventdetectoroemadapter/index.md)

- [Audio](../_audio/index.md)