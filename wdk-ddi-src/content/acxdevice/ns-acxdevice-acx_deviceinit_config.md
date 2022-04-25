---
UID: NS:acxdevice._ACX_DEVICEINIT_CONFIG
tech.root: audio
title: ACX_DEVICEINIT_CONFIG
ms.date: 01/31/2022
targetos: Windows
description: The ACX_DEVICEINIT_CONFIG structure provides configuration information to the class extension.
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
req.typenames: ACX_DEVICEINIT_CONFIG, *PACX_DEVICEINIT_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxdevice.h
api_name:
 - _ACX_DEVICEINIT_CONFIG
 - PACX_DEVICEINIT_CONFIG
 - ACX_DEVICEINIT_CONFIG
f1_keywords:
 - _ACX_DEVICEINIT_CONFIG
 - acxdevice/_ACX_DEVICEINIT_CONFIG
 - PACX_DEVICEINIT_CONFIG
 - acxdevice/PACX_DEVICEINIT_CONFIG
 - ACX_DEVICEINIT_CONFIG
 - acxdevice/ACX_DEVICEINIT_CONFIG
dev_langs:
 - c++
---

## -description

The **ACX_DEVICEINIT_CONFIG** structure provides configuration information to the class extension.

## -struct-fields

### -field Size

This field is set by the [ACX_DEVICE_CONFIG_INIT](nf-acxdevice-acx_device_config_init.md) function.

### -field Flags

Reserved.

### -field SynchronizationScope

A [WDF_SYNCHRONIZATION_SCOPE](../wdfobject/ne-wdfobject-_wdf_synchronization_scope.md) value specifying how the framework will synchronize execution of an object's event callback functions.

Internal only. Do not change the default value.

### -field ExecutionLevel

A [WDF_EXECUTION_LEVEL](../wdfobject/ne-wdfobject-_wdf_execution_level.md) value specifying the maximum IRQL at which the framework will call the event callback functions that a driver has supplied for a framework object.

Internal only. Do not change the default value.

### -field Context

Pointer to the context space for the class extension.

## -remarks

Instances of this structure must be initialized by calling the [ACX_DEVICEINIT_CONFIG_INIT](nf-acxdevice-acx_deviceinit_config_init.md) function. A pointer to an **ACX_DEVICEINIT_CONFIG** structure is passed as a parameter to the [AcxDeviceInitInitialize](nf-acxdevice-acxdeviceinitinitialize.md) function.

## -see-also

* [ACX_DEVICE_CONFIG_INIT](nf-acxdevice-acx_device_config_init.md)
* [AcxDeviceInitInitialize](nf-acxdevice-acxdeviceinitinitialize.md)
* [acxdevice.h header](index.md)

READY2GO

EDITCOMPLETE
