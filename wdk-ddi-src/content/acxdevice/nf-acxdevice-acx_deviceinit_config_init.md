---
UID: NF:acxdevice.ACX_DEVICEINIT_CONFIG_INIT
tech.root: audio
title: ACX_DEVICEINIT_CONFIG_INIT
ms.date: 01/31/2022
targetos: Windows
description: The ACX_DEVICEINIT_CONFIG_INIT function initializes the ACX_DEVICEINIT_CONFIG structure.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxdevice.h
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
 - acxdevice.h
api_name:
 - ACX_DEVICEINIT_CONFIG_INIT
f1_keywords:
 - ACX_DEVICEINIT_CONFIG_INIT
 - acxdevice/ACX_DEVICEINIT_CONFIG_INIT
dev_langs:
 - c++
---

## -description

The **ACX_DEVICEINIT_CONFIG_INIT** function initializes the [ACX_DEVICEINIT_CONFIG](ns-acxdevice-acx_deviceinit_config.md) structure.

## -parameters

### -param Config

A pointer to the [ACX_DEVICEINIT_CONFIG](ns-acxdevice-acx_deviceinit_config.md) structure to initialize.

## -remarks

### Example

```cpp
ACX_DEVICEINIT_CONFIG devInitCfg;
ACX_DEVICEINIT_CONFIG_INIT(&devInitCfg);
```

## -see-also

* [ACX_DEVICEINIT_CONFIG](ns-acxdevice-acx_deviceinit_config.md)
* [acxdevice.h header](index.md)

READY2GO

EDITCOMPLETE
