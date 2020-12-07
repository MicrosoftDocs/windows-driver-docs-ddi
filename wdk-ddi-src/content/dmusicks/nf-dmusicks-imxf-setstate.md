---
UID: NF:dmusicks.IMXF.SetState
title: IMXF::SetState (dmusicks.h)
description: The SetState method is used to set the state of the MIDI transform interface.
tech.root: audio
ms.date: 10/31/2018
keywords: ["IMXF::SetState"]
ms.keywords: IMXF::SetState, SetState, IMXF.SetState, IMXF::SetState, IMXF.SetState
req.header: dmusicks.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - IMXF::SetState
 - dmusicks/IMXF::SetState
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dmusicks.h
api_name:
 - IMXF.SetState
product:
 - Windows
---

# IMXF::SetState


## -description

The SetState method is used to set the state of the MIDI transform interface.

## -parameters

### -param State

Specifies the state that the filter graph is to be set to. This parameter is a KSSTATE enumeration value. For more information, see the following Remarks section.

## -returns

This method returns NTSTATUS which contains STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## -remarks

For an audio filter graph, the four KSSTATE enumeration values are interpreted as follows:
Value | State
-------------|---------------------------------------------------------------
KSSTATE_RUN | Everything is running and functioning as normal. In this state, the IMXF interface will be active and pass messages as usual.
KSSTATE_ACQUIRE | This is a transitional state that helps manage the transition between KSSTATE_RUN and KSSTATE_STOP. In this state, messages cannot be passed downstream in the filter graph. 
KSSTATE_PAUSE | This is a transitional state that helps manage the transition between KSSTATE_RUN and KSSTATE_STOP. 
KSSTATE_STOP | Everything is stopped in the current filter graph.

The behavior of the miniport driver depends on the state of the filter graph. This behavior differs for rendering (output) and capture (input).

On the output side, if the current state is anything other than KSSTATE_RUN, the IMXF interface should hold onto the data and not pass it to the hardware. If the current state is KSTATE_STOP then the miniport driver should discard any data it is given by passing that data to the allocator.

On the input side, if the input stream is in either KSSTATE_RUN or KSSTATE_PAUSE, it is legal for the miniport driver to get messages from the allocator and send them upstream to the capture sink. If the state is KSSTATE_STOP or KSSTATE_ACQUIRE and the hardware is trying to produce data, that data should be thrown away.

## -see-also

[IMXF](nn-dmusicks-imxf.md)

