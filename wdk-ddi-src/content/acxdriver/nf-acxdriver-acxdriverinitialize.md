---
UID: NF:acxdriver.AcxDriverInitialize
tech.root: audio
title: AcxDriverInitialize
ms.date: 09/30/2021
targetos: Windows
description: The AcxDriverInitialize function initializes the specified audio driver.
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
 - AcxDriverInitialize
f1_keywords:
 - AcxDriverInitialize
 - acxdriver/AcxDriverInitialize
dev_langs:
 - c++
---

## -description

The **AcxDriverInitialize** function initializes the specified audio driver.

## -parameters

### -param Driver

The **WDFDRIVER** object representing the audio driver to initialize.

### -param DriverConfig

Pointer to a [ACX_DRIVER_CONFIG](ns-acxdriver-acx_driver_config.md) structure that was previously initialized by calling the [ACX_DRIVER_CONFIG_INIT](nf-acxdriver-acx_driver_config_init.md) function.

## -returns

**AcxDriverInitialize** returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) error code.

## -remarks

### Example

TBD - review code snippet

```cpp
ACX_DRIVER_CONFIG acxCfg;
WDFDRIVER         driver;
NTSTATUS          status;

// Code to initialize the WDFDRIVER object...

// Initialize the audio driver configuration
ACX_DRIVER_CONFIG_INIT(&acxCfg);

// Initialize the audio driver
status = AcxDriverInitialize(driver, &acxCfg);

if (!NT_SUCCESS(status))
{
    // Log error...

    goto exit;
}
```

## -see-also

* [ACX_DRIVER_CONFIG](ns-acxdriver-acx_driver_config.md)
* [ACX_DRIVER_CONFIG_INIT](nf-acxdriver-acx_driver_config_init.md)

READY2GO
