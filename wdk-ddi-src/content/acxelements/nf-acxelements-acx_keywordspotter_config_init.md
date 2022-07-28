---
UID: NF:acxelements.ACX_KEYWORDSPOTTER_CONFIG_INIT
tech.root: audio 
title: ACX_KEYWORDSPOTTER_CONFIG_INIT
ms.date: 04/29/2022
targetos: Windows
description: The ACX_KEYWORDSPOTTER_CONFIG_INIT function initializes an ACX_KEYWORDSPOTTER_CONFIG structure.
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
 - ACX_KEYWORDSPOTTER_CONFIG_INIT
f1_keywords:
 - ACX_KEYWORDSPOTTER_CONFIG_INIT
 - acxelements/ACX_KEYWORDSPOTTER_CONFIG_INIT
dev_langs:
 - c++
---

## -description

The **ACX_KEYWORDSPOTTER_CONFIG_INIT** function initializes an [ACX_KEYWORDSPOTTER_CONFIG](ns-acxelements-acx_keywordspotter_config.md) structure.

## -parameters

### -param cfg

An [ACX_KEYWORDSPOTTER_CONFIG](ns-acxelements-acx_keywordspotter_config.md) structure.

## -remarks

### Example

Example usage is shown below.

```cpp
    ACX_KEYWORDSPOTTER_CONFIG       keywordSpotterCfg;
    
    ACX_KEYWORDSPOTTER_CONFIG_INIT(&keywordSpotterCfg);
```

## -see-also

- [acxelements.h header](index.md)
