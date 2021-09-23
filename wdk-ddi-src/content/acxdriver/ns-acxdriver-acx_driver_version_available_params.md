---
UID: NS:acxdriver._ACX_DRIVER_VERSION_AVAILABLE_PARAMS
tech.root: audio
title: ACX_DRIVER_VERSION_AVAILABLE_PARAMS
ms.date: 09/23/2021
targetos: Windows
description: The ACX_DRIVER_VERSION_AVAILABLE_PARAMS structure is passed as a parameter to the AcxDriverIsVersionAvailable function.
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
req.typenames: ACX_DRIVER_VERSION_AVAILABLE_PARAMS, *PACX_DRIVER_VERSION_AVAILABLE_PARAMS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxdriver.h
api_name:
 - _ACX_DRIVER_VERSION_AVAILABLE_PARAMS
 - PACX_DRIVER_VERSION_AVAILABLE_PARAMS
 - ACX_DRIVER_VERSION_AVAILABLE_PARAMS
f1_keywords:
 - _ACX_DRIVER_VERSION_AVAILABLE_PARAMS
 - acxdriver/_ACX_DRIVER_VERSION_AVAILABLE_PARAMS
 - PACX_DRIVER_VERSION_AVAILABLE_PARAMS
 - acxdriver/PACX_DRIVER_VERSION_AVAILABLE_PARAMS
 - ACX_DRIVER_VERSION_AVAILABLE_PARAMS
 - acxdriver/ACX_DRIVER_VERSION_AVAILABLE_PARAMS
dev_langs:
 - c++
---

## -description

The **ACX_DRIVER_VERSION_AVAILABLE_PARAMS** structure is passed as a parameter to the [AcxDriverIsVersionAvailable](nf-acxdriver-acxdriverisversionavailable.md) function.

## -struct-fields

### -field Size

This field is set by the [ACX_DRIVER_VERSION_AVAILABLE_PARAMS_INIT](nf-acxdriver-acx_driver_version_available_params_init.md) function.

### -field MajorVersion

The major version of the audio driver for which to check.

### -field MinorVersion

The minor version of the audio driver for which to check.

## -remarks

Instances of this structure must be initialized by calling the [ACX_DRIVER_VERSION_AVAILABLE_PARAMS_INIT](nf-acxdriver-acx_driver_version_available_params_init.md) function. A pointer to an **ACX_DRIVER_VERSION_AVAILABLE_PARAMS** structure is passed as a parameter to the [AcxDriverIsVersionAvailable](nf-acxdriver-acxdriverisversionavailable.md) function.

## -see-also

* [ACX_DRIVER_VERSION_AVAILABLE_PARAMS_INIT](nf-acxdriver-acx_driver_version_available_params_init.md)
* [AcxDriverIsVersionAvailable](nf-acxdriver-acxdriverisversionavailable.md)
