---
UID: NN:eventdetectoroemadapter.IEventDetectorOemAdapter
title: IEventDetectorOemAdapter
author: windows-driver-content
description: The IEventDetectorOemAdapter interface is used for hardware keyword spotters.
tech.root: audio
ms.assetid: c8b85e0b-cf91-4e9d-895f-66208b5493a7
ms.author: windowsdriverdev
ms.date: 02/22/2019
ms.topic: interface
req.header: eventdetectoroemadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.umdf-ver:
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
 - IEventDetectorOemAdapter
product: 
 - Windows
targetos: Windows
---

# IEventDetectorOemAdapter interface

## -description

The IEventDetectorOemAdapter interface is used for hardware keyword spotters.


## -inheritance
IEventDetectorOemAdapter interits from IUnknown.

## -members

<p>IEventDetectorOemAdapter has these methods.</p>
<table>
	<tr>
		<td>Method</td>
		<td>Description</td>
	</tr>
	<tr>
		<td>GetCapabilities</td>
		<td>Returns langauges and detector features supported by the object.</td>
	</tr>
	<tr>
		<td>GetCapabilitiesForLanguage</td>
		<td>Returns the events supported by the specific language.</td>
	</tr>
	<tr>
		<td>VerifyUserEventData</td>
		<td>Verifies the user recording for the given EVENTID.</td>
	</tr>
	<tr>
		<td>ComputeAndAddUserModelData</td>
		<td>Adds the user specific model data to an existing model data blob.</td>
	</tr>
	<tr>
		<td>BuildArmingPatternData</td>
		<td>Builds the pattern data to be used on a subsequent arm request - this is done once for each pin instance.</td>
	</tr>
	<tr>
		<td>ParseDetectionResultData</td>
		<td>Uses the input model data and SOUNDDETECTOR_PATTERNHEADER to determine the DETECTIONEVENTID,LANGID and USER detected. </td>
	</tr>
	<tr>
		<td>ReportOSDetectionResult</td>
		<td>Called to provide second stage result to OEM dll.</td>
	</tr>
</table>


## -remarks

## -remarks

This interface is the part of the Event Detector OEM interface to be used for hardware keyword spotters. For more information, see [Voice Activation](https://docs.microsoft.com/windows-hardware/drivers/audio/voice-activation).



## -see-also

- [eventdetectoroemadapter](../eventdetectoroemadapter/index.md)

- [Audio](../_audio/index.md)