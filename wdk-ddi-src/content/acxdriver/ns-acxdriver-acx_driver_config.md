---
UID: NS:acxdriver._ACX_DRIVER_CONFIG
tech.root: audio
title: ACX_DRIVER_CONFIG
ms.date: 01/31/2022
targetos: Windows
description: The ACX_DRIVER_CONFIG structure provides configuration information to the class extension.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxdriver.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_DRIVER_CONFIG, *PACX_DRIVER_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxdriver.h
api_name:
 - _ACX_DRIVER_CONFIG
 - PACX_DRIVER_CONFIG
 - ACX_DRIVER_CONFIG
f1_keywords:
 - _ACX_DRIVER_CONFIG
 - acxdriver/_ACX_DRIVER_CONFIG
 - PACX_DRIVER_CONFIG
 - acxdriver/PACX_DRIVER_CONFIG
 - ACX_DRIVER_CONFIG
 - acxdriver/ACX_DRIVER_CONFIG
dev_langs:
 - c++
---

## -description

The **ACX_DRIVER_CONFIG** structure provides configuration information to the class extension.

## -struct-fields

### -field Size

This field is set by the [ACX_DRIVER_CONFIG_INIT](nf-acxdriver-acx_driver_config_init.md) function.

### -field Flags

An [ACX_DRIVER_CONFIG_FLAGS](ne-acxdriver-acx_driver_config_flags.md) value.

## -remarks

Instances of this structure must be initialized by calling the [ACX_DRIVER_CONFIG_INIT](nf-acxdriver-acx_driver_config_init.md) function. A pointer to an **ACX_DRIVER_CONFIG** structure is passed as a parameter to the [AcxDriverInitialize](nf-acxdriver-acxdriverinitialize.md) function.

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

* [ACX_DRIVER_CONFIG_INIT](nf-acxdriver-acx_driver_config_init.md)
* [ACX_DRIVER_CONFIG_FLAGS](ne-acxdriver-acx_driver_config_flags.md)
* [AcxDriverInitialize](nf-acxdriver-acxdriverinitialize.md)
* [acxdriver.h header](index.md)
