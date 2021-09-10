---
UID: NF:acxdevice.AcxDeviceInitialize
tech.root: audio
title: AcxDeviceInitialize
ms.date: 09/02/2021
targetos: Windows
description: The AcxDeviceInitialize function initializes an audio class extension (ACX) device.
prerelease: true
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
 - AcxDeviceInitialize
f1_keywords:
 - AcxDeviceInitialize
 - acxdevice/AcxDeviceInitialize
dev_langs:
 - c++
---

## -description

The **AcxDeviceInitialize** function initializes an audio class extension (ACX) device.

## -parameters

### -param Device

Pointer to a **WDFDEVICE** representing the device to initialize.

### -param DeviceConfig

Pointer to an [ACX_DEVICE_CONFIG](ns-acxdevice-acx_device_config.md) structure that has been initialized by calling the [ACX_DEVICE_CONFIG_INIT](nf-acxdevice-acx_device_config_init.md) function.

## -returns

**AcxDeviceInitialize** returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) error code.

## -remarks

## -see-also

[ACX_DEVICE_CONFIG](ns-acxdevice-acx_device_config.md)

[ACX_DEVICE_CONFIG_INIT](nf-acxdevice-acx_device_config_init.md)

READY2GO