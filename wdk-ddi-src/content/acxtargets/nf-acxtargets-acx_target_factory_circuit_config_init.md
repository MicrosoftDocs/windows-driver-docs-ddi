---
UID: NF:acxtargets.ACX_TARGET_FACTORY_CIRCUIT_CONFIG_INIT
tech.root: audio
title: ACX_TARGET_FACTORY_CIRCUIT_CONFIG_INIT
ms.date: 07/22/2022
targetos: Windows
description: The ACX_TARGET_FACTORY_CIRCUIT_CONFIG_INIT function initializes an ACX target factory circuit config structure.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxtargets.h
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
 - acxtargets.h
api_name:
 - ACX_TARGET_FACTORY_CIRCUIT_CONFIG_INIT
f1_keywords:
 - ACX_TARGET_FACTORY_CIRCUIT_CONFIG_INIT
 - acxtargets/ACX_TARGET_FACTORY_CIRCUIT_CONFIG_INIT
dev_langs:
 - c++
---

## -description

The **ACX_TARGET_FACTORY_CIRCUIT_CONFIG_INIT** function initializes an ACX target factory circuit config structure.

## -parameters

### -param Config

A pointer to the [ACX_TARGET_FACTORY_CIRCUIT_CONFIG](ns-acxtargets-acx_target_factory_circuit_config.md) structure that will be initialized.

## -remarks

### Example

```cpp
    ACX_TARGET_FACTORY_CIRCUIT_CONFIG   targetCfg;
    ACXTARGETFACTORYCIRCUIT             target;

    ACX_TARGET_FACTORY_CIRCUIT_CONFIG_INIT(&targetCfg);
    targetCfg.SymbolicLinkName = m_SymbolicLinkName; 
```

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxtargets.h header](index.md)
 
