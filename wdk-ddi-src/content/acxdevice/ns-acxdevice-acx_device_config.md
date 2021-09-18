---
UID: NS:acxdevice._ACX_DEVICE_CONFIG
tech.root: audio
title: ACX_DEVICE_CONFIG
ms.date: 09/17/2021
targetos: Windows
description: The ACX_DEVICE_CONFIG structure provides configuration information to the class extension.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxdevice.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_DEVICE_CONFIG, *PACX_DEVICE_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxdevice.h
api_name:
 - _ACX_DEVICE_CONFIG
 - PACX_DEVICE_CONFIG
 - ACX_DEVICE_CONFIG
f1_keywords:
 - _ACX_DEVICE_CONFIG
 - acxdevice/_ACX_DEVICE_CONFIG
 - PACX_DEVICE_CONFIG
 - acxdevice/PACX_DEVICE_CONFIG
 - ACX_DEVICE_CONFIG
 - acxdevice/ACX_DEVICE_CONFIG
dev_langs:
 - c++
---

## -description

The **ACX_DEVICE_CONFIG** structure provides configuration information to the class extension.

## -struct-fields

### -field Size

This field is set by the [ACX_DEVICE_CONFIG_INIT](nf-acxdevice-acx_device_config_init.md) function.

### -field Flags

An [ACX_DEVICE_CONFIG_FLAGS](ne-acxdevice-acx_device_config_flags.md) value.

### -field Context

Pointer to the context space for the class extension.

## -remarks

Instances of this structure must be initialized by calling the [ACX_DEVICE_CONFIG_INIT](nf-acxdevice-acx_device_config_init.md) function. A pointer to an **ACX_DEVICE_CONFIG** structure is passed as a parameter to the [AcxDeviceInitialize](nf-acxdevice-acxdeviceinitialize.md) function.

## -see-also

* [ACX_DEVICE_CONFIG_INIT](nf-acxdevice-acx_device_config_init.md)
* [ACX_DEVICE_CONFIG_FLAGS](ne-acxdevice-acx_device_config_flags.md)
* [AcxDeviceInitialize](nf-acxdevice-acxdeviceinitialize.md)

READY2GO