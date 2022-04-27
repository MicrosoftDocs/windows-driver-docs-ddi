---
UID: NS:acxtargets._ACX_TARGET_CIRCUIT_CONFIG
tech.root: audio
title: ACX_TARGET_CIRCUIT_CONFIG
ms.date: 01/05/2022
targetos: Windows
description: The ACX_TARGET_CIRCUIT_CONFIG structure is used to define the target circuit configuration. 
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxtargets.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_TARGET_CIRCUIT_CONFIG, *PACX_TARGET_CIRCUIT_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxtargets.h
api_name:
 - _ACX_TARGET_CIRCUIT_CONFIG
 - PACX_TARGET_CIRCUIT_CONFIG
 - ACX_TARGET_CIRCUIT_CONFIG
f1_keywords:
 - _ACX_TARGET_CIRCUIT_CONFIG
 - acxtargets/_ACX_TARGET_CIRCUIT_CONFIG
 - PACX_TARGET_CIRCUIT_CONFIG
 - acxtargets/PACX_TARGET_CIRCUIT_CONFIG
 - ACX_TARGET_CIRCUIT_CONFIG
 - acxtargets/ACX_TARGET_CIRCUIT_CONFIG
dev_langs:
 - c++
---

## -description

The **ACX_TARGET_CIRCUIT_CONFIG** structure is used to define the target circuit configuration.

## -struct-fields

### -field Size

The length, in bytes, of this structure.

### -field Flags

Target circuit configuration flags defined by the [ACX_TARGET_CIRCUIT_CONFIG enum](ne-acxtargets-acx_target_circuit_config_flags.md).

No flag bits are currently defined. Set this member to zero - AcxTargetCircuitConfigNoFlags

### -field SymbolicLinkName

Pointer to a Unicode string that contains the name of the symbolic link for the circuit configuration.

## -remarks

Sample Pending

### Example

```cpp

```

## -see-also

- [acxtargets.h header](index.md)

TBD - Please review this topic