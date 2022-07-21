---
UID: NF:acxpin.AcxPinCreate
tech.root: audio
title: AcxPinCreate
ms.date: 04/11/2022
targetos: Windows
description: The AcxPinCreate function creates and initializes a new ACXPIN object.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxpin.h
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
 - acxpin.h
api_name:
 - AcxPinCreate
f1_keywords:
 - AcxPinCreate
 - acxpin/AcxPinCreate
dev_langs:
 - c++
---

## -description

The **AcxPinCreate** function creates and initializes a new [ACXPIN](index.md) object.

## -parameters

### -param Circuit [in]

The [ACXCIRCUIT](../acxcircuit/index.md) to which the new pin is added.

### -param Attributes [in]

Pointer to a [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure for configuration of the pin.

### -param Config [in]

Pointer to an [ACX_PIN_CONFIG](ns-acxpin-acx_pin_config.md) structure for configuration of the pin.

### -param Pin [out]

The newly created and initialized **ACXPIN** object.

## -returns

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

## -remarks

## -see-also

- [ACXPIN](index.md)
- [ACXCIRCUIT](../acxcircuit/index.md)
- [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md)
- [ACX_PIN_CONFIG](ns-acxpin-acx_pin_config.md)
- [acxpin.h header](index.md)
 
READY2GO

EDITCOMPLETE
