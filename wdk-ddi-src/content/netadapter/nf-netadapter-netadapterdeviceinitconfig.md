---
UID: NF:netadapter.NetAdapterDeviceInitConfig
title: NetAdapterDeviceInitConfig function (netadapter.h)
description: Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.
tech.root: netvista
ms.assetid: e8adef03-c1cf-46f6-8d22-21056ab1d539
ms.date: 02/06/2018
ms.topic: function
f1_keywords:
 - "netadapter/NetAdapterDeviceInitConfig"
ms.keywords: NetAdapterDeviceInitConfig
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
req.typenames: NetAdapterDeviceInitConfig
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netadapter.h
api_name: 
- NetAdapterDeviceInitConfig
product:
- Windows
targetos: Windows
product:
- Windows
---

# NetAdapterDeviceInitConfig function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.

## -parameters

### -param DeviceInit
Pointer to a **WDFDEVICE_INIT** object that the client received in its *[EvtDriverDeviceAdd](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md)* routine.

## -returns
The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

## -remarks
The client driver calls this method in its *[EvtDriverDeviceAdd](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md)* callback before it calls [WdfDeviceCreate](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

When a client driver calls **NetAdapterDeviceInitConfig**, the system-supplied NetAdapterCx.sys driver calls the following methods on behalf of the client. The client driver should not call these methods directly. Doing so may result in undefined behavior.

- [WdfDeviceInitSetReleaseHardwareOrderOnFailure](../wdfdevice/nf-wdfdevice-wdfdeviceinitsetreleasehardwareorderonfailure.md)
- [WdfDeviceInitSetDeviceType](../wdfdevice/nf-wdfdevice-wdfdeviceinitsetdevicetype.md)
- [WdfDeviceInitSetCharacteristics](../wdfdevice/nf-wdfdevice-wdfdeviceinitsetcharacteristics.md)
- [WdfDeviceInitSetIoType](../wdfdevice/nf-wdfdevice-wdfdeviceinitsetiotype.md)
- [WdfDeviceInitSetPowerPageable](../wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowerpageable.md)



## -see-also
