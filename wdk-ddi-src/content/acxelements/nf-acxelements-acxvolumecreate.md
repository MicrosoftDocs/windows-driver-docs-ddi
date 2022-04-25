---
UID: NF:acxelements.AcxVolumeCreate
tech.root: audio 
title: AcxVolumeCreate
ms.date: 10/21/2021
targetos: Windows
description: The AcxVolumeCreate function is used to create an ACX volume object that that will be associated with a circuit object parent. 
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
 - AcxVolumeCreate
f1_keywords:
 - AcxVolumeCreate
 - acxelements/AcxVolumeCreate
dev_langs:
 - c++
---

## -description

The AcxVolumeCreate function is used to create an ACX volume object that that will be associated with a circuit object parent. 

## -parameters

### -param Object

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that will be associated with the circuit. 

### -param Attributes

Additional Attributes defined using a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure that are used to set various values and to associate the volume object with the parent circuit object.

### -param Config

An initialized [ACX_VOLUME_CONFIG structure](ns-acxelements-acx_volume_config.md) that describes the configuration of the volume object.

### -param Volume

A pointer to a location that receives the handle to the newly created ACXVOLUME object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects). 

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
    NTSTATUS                        status;
    WDF_OBJECT_ATTRIBUTES           attributes;
 
    ACX_VOLUME_CALLBACKS            volumeCallbacks;
    ACX_VOLUME_CONFIG               volumeCfg;
    CODEC_VOLUME_ELEMENT_CONTEXT *  volumeCtx;

    ACX_VOLUME_CONFIG_INIT(&volumeCfg);

    volumeCfg.ChannelsCount = MAX_CHANNELS;
    volumeCfg.Minimum = VOLUME_LEVEL_MINIMUM;
    volumeCfg.Maximum = VOLUME_LEVEL_MAXIMUM;
    volumeCfg.SteppingDelta = VOLUME_STEPPING;
    volumeCfg.Callbacks = &volumeCallbacks;

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, CODEC_VOLUME_ELEMENT_CONTEXT);
    attributes.ParentObject = Circuit;

    status = AcxVolumeCreate(Circuit, &attributes, &volumeCfg, Element);
```

## -see-also

- [acxelements.h header](index.md)

READY2GO

