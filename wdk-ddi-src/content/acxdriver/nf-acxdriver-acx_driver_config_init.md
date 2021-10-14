---
UID: NF:acxdriver.ACX_DRIVER_CONFIG_INIT
tech.root: audio
title: ACX_DRIVER_CONFIG_INIT
ms.date: 09/29/2021
targetos: Windows
description: The ACX_DRIVER_CONFIG_INIT function initializes an ACX_DRIVER_CONFIG structure before calling AcxDriverInitialize.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxdriver.h
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
 - 
api_location:
 - acxdriver.h
api_name:
 - ACX_DRIVER_CONFIG_INIT
f1_keywords:
 - ACX_DRIVER_CONFIG_INIT
 - acxdriver/ACX_DRIVER_CONFIG_INIT
dev_langs:
 - c++
---

## -description

The **ACX_DRIVER_CONFIG_INIT** function initializes an [ACX_DRIVER_CONFIG](ne-acxdriver-acx_driver_config_flags.md) structure before calling the [AcxDriverInitialize](nf-acxdriver-acxdriverinitialize.md) function.

## -parameters

### -param Config

Pointer to an [ACX_DRIVER_CONFIG](ne-acxdriver-acx_driver_config_flags.md) structure.

## -remarks

### Example

```cpp
ACX_DRIVER_CONFIG acxCfg;
ACX_DRIVER_CONFIG_INIT(&acxCfg);
```

## -see-also

* [ACX_DRIVER_CONFIG](ne-acxdriver-acx_driver_config_flags.md)
* [AcxDriverInitialize](nf-acxdriver-acxdriverinitialize.md)

READY2GO
