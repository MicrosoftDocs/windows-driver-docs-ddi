---
UID: NF:acxelements.ACX_ELEMENT_CONFIG_INIT
tech.root: audio 
title: ACX_ELEMENT_CONFIG_INIT
ms.date: 09/23/2021
targetos: Windows
description: The ACX_ELEMENT_CONFIG_INIT function initializes an [ACX_ELEMENT_CONFIG](ns-acxelements-acx_element_config.md) structure.
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
 - ACX_ELEMENT_CONFIG_INIT
f1_keywords:
 - ACX_ELEMENT_CONFIG_INIT
 - acxelements/ACX_ELEMENT_CONFIG_INIT
dev_langs:
 - c++
---

## -description

The ACX_ELEMENT_CONFIG_INIT function initializes an [ACX_ELEMENT_CONFIG](ns-acxelements-acx_element_config.md) structure.

## -parameters

### -param cfg

An [ACX_ELEMENT_CONFIG](ns-acxelements-acx_element_config.md) structure.

## -remarks

### Example

Example usage is shown below.

```cpp
    ACX_ELEMENT_CONFIG      elementCfg;
    ACX_ELEMENT_CONFIG_INIT(&elementCfg);
```

## -see-also

- [acxelements.h header](index.md)

READY2G0

