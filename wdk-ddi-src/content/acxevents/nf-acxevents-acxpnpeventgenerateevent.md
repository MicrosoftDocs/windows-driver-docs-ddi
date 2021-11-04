---
UID: NF:acxevents.AcxPnpEventGenerateEvent
tech.root: audio
title: AcxPnpEventGenerateEvent
ms.date: 11/04/2021
targetos: Windows
description: The AcxPnpEventGenerateEvent function generates an acx pnp event.
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
 - AcxPnpEventGenerateEvent
f1_keywords:
 - AcxPnpEventGenerateEvent
 - acxevents/AcxPnpEventGenerateEvent
dev_langs:
 - c++
---

## -description

The AcxPnpEventGenerateEvent function generates an acx pnp event.

## -parameters

### -param Event

The ACXPNPEVENT object (described in [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects)).

### -param Payload

The event payload.

TBD - Is this always a AUDIOMODULE_CUSTOM_NOTIFICATION??? Pointer to an array of something?

### -param Size

The size of the event payload.


## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

This example code snip, shows the use of AcxPnpEventGenerateEvent.

```cpp
    if (fNewValue &&
        (parameterInfo->Flags & AUDIOMODULE_PARAMETER_FLAG_CHANGE_NOTIFICATION))
    {
        AUDIOMODULE_CUSTOM_NOTIFICATION customNotification = {0};

        customNotification.Type = AudioModuleParameterChanged;
        customNotification.ParameterChanged.ParameterId = command->ParameterId;

        status = AcxPnpEventGenerateEvent(audioModuleCtx->Event, &customNotification, (USHORT)sizeof(customNotification));
```

## -see-also

[acxcircuit.h header](index.md)

