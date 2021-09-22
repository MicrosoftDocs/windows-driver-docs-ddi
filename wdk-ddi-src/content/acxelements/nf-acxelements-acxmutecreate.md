---
UID: NF:acxelements.AcxMuteCreate
tech.root: audio 
title: AcxMuteCreate
ms.date: 09/22/2021
targetos: Windows
description: TBD - The AcxMuteCreate function is used to create an ACX mute object that that will be associated with a circuit object parent. 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxelements.h
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
 - acxelements.h
api_name:
 - AcxMuteCreate
f1_keywords:
 - AcxMuteCreate
 - acxelements/AcxMuteCreate
dev_langs:
 - c++
---

## -description

TBD - The AcxMuteCreate function is used to create an ACX mute object that that will be associated with a circuit object parent. 

## -parameters

### -param Object

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that will be associated with the circuit. TBD - conditional on something to determine if this is the parent?

### -param Attributes

Additional Attributes defined using a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure that are used to set various values and to associate the mute object with the parent WDF device object (TBD???).

### -param Config

An initialized [ACX_MUTE_CONFIG structure](ns-acxelements-acx_mute_config.md) that describes the configuration of the mute behavior.

### -param Mute

A pointer to a location that receives the handle to the newly created ACXMUTE object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects). 

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
    NTSTATUS                        status;
    WDF_OBJECT_ATTRIBUTES           attributes;

    ACX_MUTE_CALLBACKS              muteCallbacks;
    ACX_MUTE_CONFIG                 muteCfg;
    ACXMUTE                         muteElement;

    ACX_MUTE_CALLBACKS_INIT(&muteCallbacks);
    muteCallbacks.EvtAcxMuteAssignState = CodecR_EvtMuteAssignState;
    muteCallbacks.EvtAcxMuteRetrieveState = CodecR_EvtMuteRetrieveState;

    ACX_MUTE_CONFIG_INIT(&muteCfg);
    muteCfg.ChannelsCount = MAX_CHANNELS;
    muteCfg.Name = &KSAUDFNAME_WAVE_MUTE;
    muteCfg.Callbacks = &muteCallbacks;

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, CODEC_MUTE_ELEMENT_CONTEXT);
    attributes.ParentObject = Circuit;

    status = AcxMuteCreate(Circuit, &attributes, &muteCfg, &muteElement);
```

## -see-also

[acxelements.h header](index.md)

