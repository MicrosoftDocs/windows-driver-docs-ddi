---
UID: NS:acxmanager._ACX_CIRCUIT_TEMPLATE_CONFIG
tech.root: audio
title: ACX_CIRCUIT_TEMPLATE_CONFIG
ms.date: 04/27/2022
targetos: Windows
description: The ACX_CIRCUIT_TEMPLATE_CONFIG structure is used to configure a new ACX circuit template object.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxmanager.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_CIRCUIT_TEMPLATE_CONFIG, *PACX_CIRCUIT_TEMPLATE_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxmanager.h
api_name:
 - _ACX_CIRCUIT_TEMPLATE_CONFIG
 - PACX_CIRCUIT_TEMPLATE_CONFIG
 - ACX_CIRCUIT_TEMPLATE_CONFIG
f1_keywords:
 - _ACX_CIRCUIT_TEMPLATE_CONFIG
 - acxmanager/_ACX_CIRCUIT_TEMPLATE_CONFIG
 - PACX_CIRCUIT_TEMPLATE_CONFIG
 - acxmanager/PACX_CIRCUIT_TEMPLATE_CONFIG
 - ACX_CIRCUIT_TEMPLATE_CONFIG
 - acxmanager/ACX_CIRCUIT_TEMPLATE_CONFIG
dev_langs:
 - c++
---

## -description

The **ACX_CIRCUIT_TEMPLATE_CONFIG** structure is used to configure a new ACX circuit template object.

## -struct-fields

### -field Size

The size of all of the data in the **ACX_CIRCUIT_TEMPLATE_CONFIG** structure in bytes. This field is set by the [ACX_CIRCUIT_TEMPLATE_CONFIG_INIT](nf-acxmanager-acx_circuit_template_config_init.md) function.

### -field Flags

A combination of values from the [ACX_CIRCUIT_TEMPLATE_CONFIG_FLAGS](ne-acxmanager-acx_circuit_template_config_flags.md) enum that describe the circuit template.

### -field ContainerId

An optional GUID that specifies the ID of the circuit container.

### -field FactoryProperties

An **ACXOBJECTBAG** with the factory properties for the circuit-on-demand option.

### -field FactoryId

The GUID value of the factory circuit ID. Mutually exclusive with *FactoryUri*.

### -field FactoryUri

A Unicode string containing the fully qualified factory resource ID. Mutually exclusive with the *FactoryId*.

### -field FactoryName

Set to `NULL`.

### -field CircuitProperties

An **ACXOBJECTBAG** with the circuit properties for the *not* circuit-on-demand option.

### -field CircuitId

The GUID value of the circuit ID. Mutually exclusive with *CircuitUri*.

### -field CircuitUri

A Unicode string containing the fully qualified circuit resource ID. Mutually exclusive with the *CircuitId*.

### -field CircuitName

Set to `NULL`.

## -remarks

The **ACX_CIRCUIT_TEMPLATE_CONFIG** structure is initialized by calling the [ACX_CIRCUIT_TEMPLATE_CONFIG_INIT](nf-acxmanager-acx_circuit_template_config_init.md) function.

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [ACX_CIRCUIT_TEMPLATE_CONFIG_INIT](nf-acxmanager-acx_circuit_template_config_init.md)
- [ACX_CIRCUIT_TEMPLATE_CONFIG_FLAGS](ne-acxmanager-acx_circuit_template_config_flags.md)
- [acxmanager.h header](index.md)
