---
UID: NF:acxelements.AcxElementCreate
tech.root: audio
title: AcxElementCreate
ms.date: 12/15/2022
targetos: Windows
description: The AcxElementCreate function is used to create an ACXELEMENT object that that will be associated with a circuit or stream device object parent.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxelements.h
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
 - HeaderDef
api_location:
 - acxelements.h
api_name:
 - AcxElementCreate
f1_keywords:
 - AcxElementCreate
 - acxelements/AcxElementCreate
dev_langs:
 - c++
---

## -description

The **AcxElementCreate** function is used to create an ACXELEMENT object that that will be associated with a circuit or stream device object parent.

## -parameters

### -param Object

A WDFDEVICE object (described in [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that that will be associated with the stream or circuit.

### -param Attributes

Additional Attributes defined using a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure that are used to set various values and to associate the ACX element with the parent stream or circuit object.

### -param Config

An initialized [ACX_ELEMENT_CONFIG structure](ns-acxelements-acx_element_config.md) that describes the configuration of the element.

### -param Element

A pointer to a location that receives the handle to the newly created ACXELEMENT object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
    NTSTATUS                        status;
    WDF_OBJECT_ATTRIBUTES           attributes;

    ACXSTREAM                       stream;

    ACXELEMENT                      elements[2] = {0};
    ACX_ELEMENT_CONFIG              elementCfg;
    CODEC_ELEMENT_CONTEXT *         elementCtx;

    ACX_ELEMENT_CONFIG_INIT(&elementCfg);
    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, CODEC_ELEMENT_CONTEXT);
    attributes.ParentObject = stream;

    status = AcxElementCreate(stream, &attributes, &elementCfg, &elements[0]);
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header](index.md)
