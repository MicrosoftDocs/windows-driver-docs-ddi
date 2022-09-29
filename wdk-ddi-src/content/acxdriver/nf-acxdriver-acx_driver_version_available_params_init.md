---
UID: NF:acxdriver.ACX_DRIVER_VERSION_AVAILABLE_PARAMS_INIT
tech.root: audio
title: ACX_DRIVER_VERSION_AVAILABLE_PARAMS_INIT
ms.date: 01/31/2022
targetos: Windows
description: The ACX_DRIVER_VERSION_AVAILABLE_PARAMS_INIT function initializes an ACX_DRIVER_VERSION_AVAILABLE_PARAMS structure before calling the AcxDriverIsVersionAvailable function.
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
 - LibDef
api_location:
 - acxdriver.h
api_name:
 - ACX_DRIVER_VERSION_AVAILABLE_PARAMS_INIT
f1_keywords:
 - ACX_DRIVER_VERSION_AVAILABLE_PARAMS_INIT
 - acxdriver/ACX_DRIVER_VERSION_AVAILABLE_PARAMS_INIT
dev_langs:
 - c++
---

## -description

The **ACX_DRIVER_VERSION_AVAILABLE_PARAMS_INIT** function initializes an [ACX_DRIVER_VERSION_AVAILABLE_PARAMS](ns-acxdriver-acx_driver_version_available_params.md) structure before calling the [AcxDriverIsVersionAvailable](nf-acxdriver-acxdriverisversionavailable.md) function.

## -parameters

### -param Params

Pointer to an [ACX_DRIVER_VERSION_AVAILABLE_PARAMS](ns-acxdriver-acx_driver_version_available_params.md) structure.

### -param MajorVersion

The major version of the audio driver for which to check.

### -param MinorVersion

The minor version of the audio driver for which to check.

## -remarks

### Example

```cpp
ACX_DRIVER_VERSION_AVAILABLE_PARAMS ver;
ACX_DRIVER_VERSION_AVAILABLE_PARAMS_INIT(&ver, 1, 0);
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

* [ACX_DRIVER_VERSION_AVAILABLE_PARAMS](ns-acxdriver-acx_driver_version_available_params.md)
* [AcxDriverIsVersionAvailable](nf-acxdriver-acxdriverisversionavailable.md)
* [acxdriver.h header](index.md)

