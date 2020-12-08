---
UID: NF:usbpmapi.UsbPm_Deregister
title: UsbPm_Deregister function (usbpmapi.h)
description: Unregisters the client driver with the Policy Manager.
ms.date: 09/30/2018
keywords: ["UsbPm_Deregister function"]
ms.keywords: UsbPm_Deregister
tech.root: usbref
req.header: usbpmapi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: 2.27
req.lib: UsbPmApi.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - UsbPm_Deregister
 - usbpmapi/UsbPm_Deregister
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - UsbPmApi.lib
api_name:
 - UsbPm_Deregister
---

# UsbPm_Deregister function


## -description

Unregisters the client driver with the Policy Manager.

## -parameters

### -param ClientHandle

[In] The handle that the client driver received in a previous call to [**UsbPm_Register**](nf-usbpmapi-usbpm_register.md).

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) value.

## -remarks

[**UsbPm_Deregister**] does not return until all outstanding calls to the client driver's callback functions are returned. After **UsbPm_Deregister** returns, Policy Manager no longer invokes callback functions on the same handle.

The driver typically calls **UsbPm_Register** in the driver's [**EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT**](../wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_init.md) and unregisters in [**EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP**](../wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup.md) by calling [**UsbPm_Deregister**](nf-usbpmapi-usbpm_deregister.md).

## -see-also

[**UsbPm_Register**](nf-usbpmapi-usbpm_register.md)
