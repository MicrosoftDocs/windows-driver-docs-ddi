---
UID: NF:acxdevice.AcxDeviceInitInitialize
tech.root: audio
title: AcxDeviceInitInitialize
ms.date: 09/30/2021
targetos: Windows
description: The client driver must call AcxDeviceInitInitialize in its EVT_WDF_DRIVER_DEVICE_ADD callback, before calling WdfDeviceCreate.
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
 - AcxDeviceInitInitialize
f1_keywords:
 - AcxDeviceInitInitialize
 - acxdevice/AcxDeviceInitInitialize
dev_langs:
 - c++
---

## -description

The client driver must call **AcxDeviceInitInitialize** in its [EVT_WDF_DRIVER_DEVICE_ADD](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) callback, before calling [WdfDeviceCreate](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

## -parameters

### -param DeviceInit

Pointer to a [WDFDEVICE_INIT](/windows-hardware/drivers/wdf/wdfdevice_init) structure representing the device to initialize.

### -param Config

Pointer to an [ACX_DEVICEINIT_CONFIG](ns-acxdevice-acx_deviceinit_config.md) structure that has been initialized by calling the [ACX_DEVICEINIT_CONFIG_INIT](nf-acxdevice-acx_deviceinit_config_init.md) function.

## -returns

**AcxDeviceInitInitialize** returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) error code.

## -remarks

### Example

TBD - review code snippet

```cpp
WDFDEVICE             Parent;
NTSTATUS              status;
PWDFDEVICE_INIT       devInit = NULL;
ACX_DEVICEINIT_CONFIG devInitCfg;

// Code to initialize WDFDEVICE...

//
// Create a child audio device for this circuit.
//
devInit = WdfPdoInitAllocate(Parent);

if (NULL == devInit) 
{
    status = STATUS_INSUFFICIENT_RESOURCES;
    ASSERT(FALSE);
    goto exit;
}

//
// Allow ACX to add any pre-requirement it needs on this device.
//
ACX_DEVICEINIT_CONFIG_INIT(&devInitCfg);

devInitCfg.Flags |= AcxDeviceInitConfigRawDevice; 

status = AcxDeviceInitInitialize(devInit, &devInitCfg);

if (!NT_SUCCESS(status)) 
{
    ASSERT(FALSE);
    goto exit;
}
```

## -see-also

* [EVT_WDF_DRIVER_DEVICE_ADD](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md)
* [WdfDeviceCreate](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md)
* [WDFDEVICE_INIT](/windows-hardware/drivers/wdf/wdfdevice_init)
* [ACX_DEVICEINIT_CONFIG](ns-acxdevice-acx_deviceinit_config.md)
* [ACX_DEVICEINIT_CONFIG_INIT](nf-acxdevice-acx_deviceinit_config_init.md)
* [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values)
