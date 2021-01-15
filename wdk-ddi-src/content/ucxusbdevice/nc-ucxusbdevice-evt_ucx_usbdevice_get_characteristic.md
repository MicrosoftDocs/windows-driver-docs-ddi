---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_GET_CHARACTERISTIC
title: EVT_UCX_USBDEVICE_GET_CHARACTERISTIC (ucxusbdevice.h)
description: UCX invokes this callback to retrieve the device characteristics.
old-location: buses\evt_ucx_usbdevice_get_characteristic.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["EVT_UCX_USBDEVICE_GET_CHARACTERISTIC callback function"]
ms.keywords: "*PFN_UCX_USBDEVICE_GET_CHARACTERISTIC, *PFN_UCX_USBDEVICE_GET_CHARACTERISTIC callback function pointer [Buses], EVT_UCX_USBDEVICE_GET_CHARACTERISTIC, EVT_UCX_USBDEVICE_GET_CHARACTERISTIC callback, EvtUcxDeviceGetCharacteristic, EvtUcxDeviceGetCharacteristic callback function [Buses], buses.evt_ucx_usbdevice_get_characteristic, ucxusbdevice/EvtUcxDeviceGetCharacteristic"
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_UCX_USBDEVICE_GET_CHARACTERISTIC
 - ucxusbdevice/EVT_UCX_USBDEVICE_GET_CHARACTERISTIC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ucxusbdevice.h
api_name:
 - EVT_UCX_USBDEVICE_GET_CHARACTERISTIC
---

# EVT_UCX_USBDEVICE_GET_CHARACTERISTIC callback function


## -description

 UCX invokes this callback to retrieve the device characteristics.

## -parameters

### -param UcxController 

[in]
 A handle to the UCX controller that the client driver received in a previous call to  the <a href="/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a> method.

### -param UcxUsbDevice 

[in]
A handle to a UCX object that represents the USB device that the client driver received in a previous call to the <a href="/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucxusbdevicecreate">UcxUsbDeviceCreate</a> method.

### -param UcxUsbDeviceCharacteristic 

[in, out]
A pointer to a <a href="/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_ucx_usbdevice_characteristic">UCX_USBDEVICE_CHARACTERISTIC</a> structure that contains the type of characteristic in which the caller is interested. The client driver fills the value of the requested  characteristic. For example, if the type indicates <a href="/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_ucx_usbdevice_characteristic_path_delay">UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY</a>, the driver fills the <b>UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY</b> structure, pointed to by <b>PathDelay</b> member, with the appropriate maximum and send path delay values.

## -returns

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.

## -remarks

The UCX client driver registers its implementation with the USB host controller extension (UCX) by calling the <a href="/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucxusbdevicecreate">UcxUsbDeviceCreate</a> method.

