---
UID: NF:acxpin.AcxJackCreate
tech.root: audio
title: AcxJackCreate
ms.date: 01/20/2022
targetos: Windows
description: The AcxJackCreate function creates and initializes a new audio jack object.
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
 - AcxJackCreate
f1_keywords:
 - AcxJackCreate
 - acxpin/AcxJackCreate
dev_langs:
 - c++
---

## -description

The **AcxJackCreate** function creates and initializes a new audio jack object.

## -parameters

### -param AcxPin [in]

The pin object associated with the jack.

### -param Attributes [in]

A pointer to the [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure to use when creating the jack.

### -param Config [in]

A pointer to an [ACX_JACK_CONFIG](ns-acxpin-acx_jack_config.md) structure to use when creating the jack.

### -param Jack [out]

A pointer to the newly created jack object.

## -returns

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

## -remarks

## -see-also

- [ACX_JACK_CONFIG](ns-acxpin-acx_jack_config.md)
- [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values)
