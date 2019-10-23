---
UID: NF:ucmucsidevice.UcmUcsiDeviceInitialize
title: UcmUcsiDeviceInitialize function (ucmucsidevice.h)
tech.root: usbref
description: Initializes the UCSI extension (UcmUcsiCx).
ms.assetid: 8ad48691-2cca-4aaf-b61d-3127001c3180
ms.date: 09/30/2018
ms.topic: function
f1_keywords:
 - "ucmucsidevice/UcmUcsiDeviceInitialize"
ms.keywords: UcmUcsiDeviceInitialize
req.header: ucmucsidevice.h
req.include-header: UcmUcsiCx.h 
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.lib: UcmUcsiCxStub.lib
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- LibDef
api_location: 
- UcmUcsiCxStub.lib
api_name: 
- UcmUcsiDeviceInitialize
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# UcmUcsiDeviceInitialize function


## -description

Initializes the UCSI extension (UcmUcsiCx).

## -parameters

### -param WdfDevice
A handle to a framework device object that the client driver received in a previous call to [**WdfDeviceCreate**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate).

### -param Config
A pointer to a caller-supplied [**UCMUCSI_DEVICE_CONFIG**](ns-ucmucsidevice-_ucmucsi_device_config.md) structure that is initialized by calling [**UCMUCSI_DEVICE_CONFIG_INIT**](nf-ucmucsidevice-ucmucsi_device_config_init.md).

## -returns
Returns STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate [NTSTATUS](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values) code.

## -remarks
The client driver must call **UcmUcsiDeviceInitialize** in the driver's [**EVT_WDF_DRIVER_DEVICE_ADD**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add) implementation after calling [**WdfDeviceCreate**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate) successfully.

## -see-also

[**EVT_WDF_DRIVER_DEVICE_ADD**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add)

[**UCMUCSI_DEVICE_CONFIG**](ns-ucmucsidevice-_ucmucsi_device_config.md)

[**UCMUCSI_DEVICE_CONFIG_INIT**](nf-ucmucsidevice-ucmucsi_device_config_init.md)

[**WdfDeviceCreate**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate)
