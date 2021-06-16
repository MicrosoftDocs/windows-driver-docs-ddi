---
UID: NF:hidspicx.HidSpiCxDeviceInitConfig
tech.root: hid
title: HidSpiCxDeviceInitConfig
ms.date: 06/14/2021
targetos: Windows
description: 
prerelease: true
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
req.target-min-winverclnt: WIN10_NEXT
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
 - HidSpiCxDeviceInitConfig
f1_keywords:
 - HidSpiCxDeviceInitConfig
 - hidspicx/HidSpiCxDeviceInitConfig
dev_langs:
 - c++
---

## -description

The client driver must call **HidSpiCxDeviceInitConfig** in its [EVT_WDF_DRIVER_DEVICE_ADD](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) callback, before calling [WdfDeviceCreate](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

## -parameters

### -param DeviceInit

A pointer to a [WDFDEVICE_INIT](/windows-hardware/drivers/wdf/wdfdevice_init) object that the client received in its [EVT_WDF_DRIVER_DEVICE_ADD](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) routine.

## -returns

[NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) indicating whether the class extension was able to successfully initialize the structure.

## -remarks

The class extension initializes private Plug-and-Play and power hooks for the device.

## -see-also

[EVT_WDF_DRIVER_DEVICE_ADD](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md)

[WdfDeviceCreate](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md)
