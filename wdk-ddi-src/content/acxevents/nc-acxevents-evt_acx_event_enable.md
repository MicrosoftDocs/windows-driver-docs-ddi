---
UID: NC:acxevents.EVT_ACX_EVENT_ENABLE
tech.root: audio
title: EVT_ACX_EVENT_ENABLE
ms.date: 12/13/2021
targetos: Windows
description: The EVT_ACX_EVENT_ENABLE callback is used by the driver to enabled the ACXEVENT source.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxevents.h
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
 - acxevents.h
api_name:
 - EVT_ACX_EVENT_ENABLE
f1_keywords:
 - EVT_ACX_EVENT_ENABLE
 - acxevents/EVT_ACX_EVENT_ENABLE
dev_langs:
 - c++
---

## -description

The **EVT_ACX_EVENT_ENABLE** callback is used by the driver to enabled the ACXEVENT source.

## -parameters

### -param Event

The ACXEVENT object (described in [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects)).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

This sample shows the use of the EVT_ACX_EVENT_ENABLE callback.

```cpp
    //
    // Add enable/disable callbacks for this element.
    //
    ACX_EVENT_CALLBACKS_INIT(&eventCallbacks);
    eventCallbacks.EvtAcxEventEnable = &TestElement::EvtEventEnableCallback; 
    eventCallbacks.EvtAcxEventDisable = &TestElement::EvtEventDisableCallback;

    ACX_EVENT_CONFIG_INIT(&eventCfg);

NTSTATUS
TestElement::EvtEventEnableCallback(
    _In_ ACXEVENT Event
    )
{
    TEST_EVENT_CONTEXT * eventCtx;
    TestElement * This;
    
    PAGED_CODE();

    eventCtx = GetTestEventContext(Event);
    ASSERT(eventCtx != NULL);
    ASSERT(eventCtx->TestElement != NULL);

    This = eventCtx->TestElement;

    // Add code to enable event source.    

    return STATUS_SUCCESS;
}
```

## -see-also

- [acxevents.h header](index.md)

READY2GO
