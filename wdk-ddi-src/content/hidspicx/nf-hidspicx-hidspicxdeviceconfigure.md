---
UID: NF:hidspicx.HidSpiCxDeviceConfigure
tech.root: hid
title: HidSpiCxDeviceConfigure
ms.date: 06/14/2021
targetos: Windows
description: 
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: hidspicx.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11
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
 - hidspicx.h
api_name:
 - HidSpiCxDeviceConfigure
f1_keywords:
 - HidSpiCxDeviceConfigure
 - hidspicx/HidSpiCxDeviceConfigure
dev_langs:
 - c++
---

## -description

After calling [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md), and still in its [**EVT_WDF_DRIVER_DEVICE_ADD**](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) callback, the client driver calls this function with a pointer to a [**HIDSPICX_DEVICE_CONFIG**](ns-hidspicx-hidspicx_device_config.md) structure, specifying interfaces the class extension will use to communicate with the device. The class extension initializes its internal state, returning whether or not this is successful.

## -parametersDone

### -param Device

A handle to a framework device object the client driver obtained from a previous call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param DeviceConfiguration

Pointer to an initialized [**HIDSPICX_DEVICE_CONFIG**](ns-hidspicx-hidspicx_device_config.md) structure, specifying the details of the callbacks and queues to be used for communication between the class extension and client driver.

## -returns

[**NTSTATUS**](/windows-hardware/drivers/kernel/using-ntstatus-values) indicating whether the class extension was able to successfully configure the device.

## -remarks

The class extension initializes the internal state, returning whether or not this is successful.

The client driver may create a default queue before or after making this callback, in order to handle IOCTLs not handled by the class extension.

Client drivers should not attempt to acquire power policy ownership to configure power policy settings. [HidClass](../hidclass/index.md) and [HidSpiCx](index.md) are responsible for managing the power policy of the device.

## -see-also

[**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md)

[**EVT_WDF_DRIVER_DEVICE_ADD**](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md)

[**HIDSPICX_DEVICE_CONFIG**](ns-hidspicx-hidspicx_device_config.md)

[HIDSPICX_REPORT](ns-hidspicx-hidspicx_report.md)
