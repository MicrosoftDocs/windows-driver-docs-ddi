---
UID: NF:acxevents.AcxPnpEventGenerateEvent
tech.root: audio
title: AcxPnpEventGenerateEvent
ms.date: 12/16/2022
targetos: Windows
description: The AcxPnpEventGenerateEvent function generates an ACX PNP event.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxevents.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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

The **AcxPnpEventGenerateEvent** function generates an ACX PNP event.

## -parameters

### -param Event

The ACXPNPEVENT object (described in [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects)).

### -param Payload

The event payload.

### -param Size

The size of the event payload.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

The Payload is specific to the type of PNP event generated.

An ACXPNPEVENT represents an asynchronous notification available at the driver level. PNP events can be added to any objects. Currently they are used with ACXAUDIOMODULE and ACXKEYWARDSPOTTER objects. Internally ACXPNPEVENTs are exposed as PNP asynchronous notification to upper layers.

### Example

This example code snip, shows the use of AcxPnpEventGenerateEvent.

```cpp
        AUDIOMODULE_CUSTOM_NOTIFICATION customNotification = {0};

        customNotification.Type = AudioModuleParameterChanged;
        customNotification.ParameterChanged.ParameterId = command->ParameterId;

        status = AcxPnpEventGenerateEvent(audioModuleCtx->Event, &customNotification, (USHORT)sizeof(customNotification));
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxevents.h header](index.md)
