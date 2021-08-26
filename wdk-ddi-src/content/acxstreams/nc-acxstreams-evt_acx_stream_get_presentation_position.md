---
UID: NC:acxstreams.EVT_ACX_STREAM_GET_PRESENTATION_POSITION
tech.root: audio
title: EVT_ACX_STREAM_GET_PRESENTATION_POSITION
ms.date: 07/07/2021
targetos: Windows
description: The EvtAcxStreamGetPresentationPosition tells the driver to indicate the current position along with the QPC value at the time the current position was calculated. 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxstreams.h
api_name:
 - EVT_ACX_STREAM_GET_PRESENTATION_POSITION
f1_keywords:
 - EVT_ACX_STREAM_GET_PRESENTATION_POSITION
 - acxstreams/EVT_ACX_STREAM_GET_PRESENTATION_POSITION
dev_langs:
 - c++
---

## -description

The EvtAcxStreamGetPresentationPosition tells the driver to indicate the current position along with the QPC value at the time the current position was calculated. 

## -parameters

### -param Stream

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An ACXSTREAM object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param PositionInBlocks

This is the position in blocks of the current stream (TBD?). This is a zero/one (TBD?) based position.

### -param QPCPosition

The query performance counter value  that provides a time stamp for the first audio frame in the data packet. This timestamp is expressed in 100-nanosecond (1000? TBD) units. This field can be set to null (zero?) if not being used (TBD?).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).



## -remarks

### Example

TBD - no sample driver code found

Example usage is shown below.

```cpp

```


## -see-also

[acxstreams.h header](index.md)

