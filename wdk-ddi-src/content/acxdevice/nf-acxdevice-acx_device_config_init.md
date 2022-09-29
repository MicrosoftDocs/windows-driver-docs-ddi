---
UID: NF:acxdevice.ACX_DEVICE_CONFIG_INIT
tech.root: audio
title: ACX_DEVICE_CONFIG_INIT
ms.date: 01/31/2022
targetos: Windows
description: The ACX_DEVICE_CONFIG_INIT function initializes an ACX_DEVICE_CONFIG structure to be used when calling the AcxDeviceInitialize function.
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
 - ACX_DEVICE_CONFIG_INIT
f1_keywords:
 - ACX_DEVICE_CONFIG_INIT
 - acxdevice/ACX_DEVICE_CONFIG_INIT
dev_langs:
 - c++
---

## -description

The **ACX_DEVICE_CONFIG_INIT** function initializes an [ACX_DEVICE_CONFIG](ns-acxdevice-acx_device_config.md) structure to be used when calling the [AcxDeviceInitialize](nf-acxdevice-acxdeviceinitialize.md) function.

## -parameters

### -param Config

Pointer to an [ACX_DEVICE_CONFIG](ns-acxdevice-acx_device_config.md) structure.

## -remarks

### Example

```cpp
ACX_DEVICE_CONFIG devCfg;
ACX_DEVICE_CONFIG_INIT(&devCfg);
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

* [ACX_DEVICE_CONFIG](ns-acxdevice-acx_device_config.md)
* [AcxDeviceInitialize](nf-acxdevice-acxdeviceinitialize.md)
* [acxdevice.h header](index.md)

