---
UID: NC:acxrequest.EVT_ACX_OBJECT_PROCESS_EVENT_REQUEST
tech.root: audio
title: EVT_ACX_OBJECT_PROCESS_EVENT_REQUEST
ms.date: 07/26/2022
targetos: Windows
description: The EVT_ACX_OBJECT_PROCESS_EVENT_REQUEST callback is used by the driver to handle event notifications. 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxrequest.h
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
 - LibDef
api_location:
 - acxrequest.h
api_name:
 - EVT_ACX_OBJECT_PROCESS_EVENT_REQUEST
f1_keywords:
 - EVT_ACX_OBJECT_PROCESS_EVENT_REQUEST
 - acxrequest/EVT_ACX_OBJECT_PROCESS_EVENT_REQUEST
dev_langs:
 - c++
---

## -description

The **EVT_ACX_OBJECT_PROCESS_EVENT_REQUEST** callback is used by the driver to handle event notifications. 

## -parameters

### -param Object

An ACX object associated with the request.

### -param Event

The ACXEVENT object (described in [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects)). An AcxEvent object that represents an asynchronous notification available at the driver level. Events can be added to AcxCircuits, AcxStreams, AcxElements and AcxPins. Internally they are exposed as KS events to upper layers.

### -param Verb

An verb from the [ACX_EVENT_VERB](ne-acxrequest-acx_event_verb.md) enumeration that describes the type of operation.

### -param EventData

An optional ACXEVENTDATA ACX object that provides information about the event.

### -param Request

An optional WDFREQUEST object associated with this operation.

For more information about working with WDF request objects, see [Creating Framework Request Objects](/windows-hardware/drivers/wdf/creating-framework-request-objects) and [wdfrequest.h header](/windows-hardware/drivers/ddi/wdfrequest/).

## -remarks

### Example

Example usage is shown below.

```cpp

EVT_ACX_OBJECT_PROCESS_EVENT_REQUEST CodecR_EvtMuteElementChangeEventCallback;

...


VOID
CodecR_EvtMuteElementChangeEventCallback(
    _In_        ACXOBJECT       Object,
    _In_        ACXEVENT        Event,
    _In_        ACX_EVENT_VERB  Verb,
    _In_opt_    ACXEVENTDATA    EventData,
    _In_opt_    WDFREQUEST      Request
    )
{
    NTSTATUS                    status = STATUS_NOT_SUPPORTED;
    PCODEC_MUTE_ELEMENT_CONTEXT muteCtx = NULL;
    CODEC_MUTE_EVENT_CONTEXT *  muteEventCtx;
    
    PAGED_CODE();
    
    muteCtx = GetCodecMuteElementContext(Object);
    ASSERT(muteCtx);

    // for testing. 
    muteEventCtx = GetCodecMuteEventContext(Event);
    ASSERT(muteEventCtx);

    //
    // Take the correct action: enable/disable.
    //
    switch (Verb)
    {
    case AcxEventVerbEnable:
        AcxEventAddEventData(Event, EventData);
        WdfTimerStart(muteEventCtx->Timer, WDF_REL_TIMEOUT_IN_MS(10));
        status = STATUS_SUCCESS;
        break;
        
    case AcxEventVerbBasicSupport:
        status = STATUS_SUCCESS;
        break;
        
    case AcxEventVerbDisable:
        ASSERT(Request == NULL);
        //
        // Verb is AcxEventVerbDisable;
        // It is ok to generate events even if no one is listening.
        // If present, ACX completes the request associated with this action.
        //
        break;
        
    default:
        ASSERT(FALSE);
        status = STATUS_INVALID_DEVICE_REQUEST;
        break;
    }

    if (Request != NULL)
    {
        WdfRequestComplete(Request, status); 
    }
}

```

## -see-also

- [acxrequest.h header](index.md)


