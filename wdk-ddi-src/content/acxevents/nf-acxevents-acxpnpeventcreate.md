---
UID: NF:acxevents.AcxPnpEventCreate
tech.root: audio
title: AcxPnpEventCreate
ms.date: 11/02/2021
targetos: Windows
description: The AcxPnpEventCreate function creates an pnp event.
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
 - AcxPnpEventCreate
f1_keywords:
 - AcxPnpEventCreate
 - acxevents/AcxPnpEventCreate
dev_langs:
 - c++
---

## -description

The **AcxPnpEventCreate** function creates an ACX pnp event.

## -parameters

### -param Device

TBD - An existing WDFDEVICE object (described in [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that TBD has/is will be the - TBD TBD 

### -param Object

TBD - An ACXAUDIOMODULE object that is described in [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects) that will be associated with the event.

### -param Attributes

Additional Attributes defined using a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) that are used to set the various object’s values: cleanup and destroy callbacks, context type, and to specify its parent object.

### -param Config

An [ACX_PNPEVENT_CONFIG](ns-acxevents-acx_pnpevent_config.md) structure that defines the configuration for an ACX PnP event.

### -param Event

The ACXEVENT object (described in [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects)).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

An AcxPnpEvent represents an asynchronous notification available at the driver level. PnP events can be added to any objects. Currently they are used with AcxModule and AcxKeywordSpotter objects. Internally AcxPnpEvents are exposed as PnP asynchronous notification to upper layers. 

### Example

This example code shows the use of AcxPnpEventCreate.

```cpp
    NTSTATUS                        status;
    ACXAUDIOMODULE                  audioModuleElement;
    WDF_OBJECT_ATTRIBUTES           attributes;
    ACX_PNPEVENT_CONFIG             audioModuleEventCfg;
    ACXPNPEVENT                     audioModuleEvent;

    status = AcxAudioModuleCreate(Circuit, &attributes, &audioModuleCfg, &audioModuleElement);

    audioModule0Ctx = GetCodecAudioModule0Context(audioModuleElement);

    ACX_PNPEVENT_CONFIG_INIT(&audioModuleEventCfg);

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, CODEC_PNPEVENT_CONTEXT);
    attributes.ParentObject = audioModuleElement;
    status = AcxPnpEventCreate(Device, audioModuleElement, &attributes, &audioModuleEventCfg, &audioModuleEvent);
```

## -see-also

- [acxevents.h header](index.md)

TBD - Please review this topic

