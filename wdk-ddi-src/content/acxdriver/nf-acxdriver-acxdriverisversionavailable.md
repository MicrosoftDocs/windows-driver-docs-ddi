---
UID: NF:acxdriver.AcxDriverIsVersionAvailable
tech.root: audio
title: AcxDriverIsVersionAvailable
ms.date: 01/31/2022
targetos: Windows
description: The AcxDriverIsVersionAvailable function returns a Boolean value indicating if the specified driver version is available.
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
 - AcxDriverIsVersionAvailable
f1_keywords:
 - AcxDriverIsVersionAvailable
 - acxdriver/AcxDriverIsVersionAvailable
dev_langs:
 - c++
---

## -description

The **AcxDriverIsVersionAvailable** function returns a Boolean value indicating if the specified driver version is available.

## -parameters

### -param Driver

The **WDFDRIVER** object to check for the version specified by *VersionAvailableParams*.

### -param VersionAvailableParams

Pointer to an [ACX_DRIVER_VERSION_AVAILABLE_PARAMS](ns-acxdriver-acx_driver_version_available_params.md) structure that indicates the version of the audio driver you are seeking.

## -returns

**AcxDriverIsVersionAvailable** returns a Boolean value indicating if the specified driver version is available.

## -remarks

Call the [ACX_DRIVER_VERSION_AVAILABLE_PARAMS_INIT](nf-acxdriver-acx_driver_version_available_params_init.md) function to initialize the *VersionAvailableParams* structure before calling this function.

### Example

```cpp
WDFDRIVER                           driver;
ACX_DRIVER_VERSION_AVAILABLE_PARAMS ver;

// Code to initialize the WDFDRIVER object...

// Initialize the audio driver version available structure
ACX_DRIVER_VERSION_AVAILABLE_PARAMS_INIT(&ver, 1, 0);

// Check if version 1.0 is available
if (!AcxDriverIsVersionAvailable(driver, &ver)) 
{
    DbgPrint("Unexpected library version.\n");
    return STATUS_REVISION_MISMATCH;
}
```

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

* [ACX_DRIVER_VERSION_AVAILABLE_PARAMS](ns-acxdriver-acx_driver_version_available_params.md)
* [ACX_DRIVER_VERSION_AVAILABLE_PARAMS_INIT](nf-acxdriver-acx_driver_version_available_params_init.md)
* [acxdriver.h header](index.md)

