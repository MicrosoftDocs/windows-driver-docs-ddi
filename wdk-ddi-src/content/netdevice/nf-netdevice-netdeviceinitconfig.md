---
UID: NF:netdevice.NetDeviceInitConfig
title: NetDeviceInitConfig function (netdevice.h)
author: windows-driver-content
description: The NetDeviceInitConfig method initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.
tech.root: netvista
ms.assetid: 578116d2-0dcf-4ebb-a42f-db9f456a0f38
ms.author: windowsdriverdev
ms.date: 10/11/2019
keywords: ["NetDeviceInitConfig function"]
ms.keywords: NetDeviceInitConfig
req.header: netdevice.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: netadaptercxstub.lib
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
ms.custom: Vb
f1_keywords:
 - NetDeviceInitConfig
 - netdevice/NetDeviceInitConfig
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netadaptercxstub.lib
api_name:
 - NetDeviceInitConfig
product:
 - Windows
---

# NetDeviceInitConfig function


## -description

The **NetDeviceInitConfig** method initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.

## -parameters

### -param DeviceInit

A pointer to a WDFDEVICE_INIT object that the client driver received in its [*EvtDriverDeviceAdd*](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) routine.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

## -remarks

A client driver calls this method in its [*EvtDriverDeviceAdd*](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) callback before it calls [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

When a client driver calls **NetDeviceInitConfig**, the system-supplied NetAdapterCx.sys driver calls the following methods on behalf of the client. The client driver should not call these methods directly. Doing so may result in undefined behavior.

- [**WdfDeviceInitSetReleaseHardwareOrderOnFailure**](../wdfdevice/nf-wdfdevice-wdfdeviceinitsetreleasehardwareorderonfailure.md)
- [**WdfDeviceInitSetDeviceType**](../wdfdevice/nf-wdfdevice-wdfdeviceinitsetdevicetype.md)
- [**WdfDeviceInitSetCharacteristics**](../wdfdevice/nf-wdfdevice-wdfdeviceinitsetcharacteristics.md)
- [**WdfDeviceInitSetIoType**](../wdfdevice/nf-wdfdevice-wdfdeviceinitsetiotype.md)
- [**WdfDeviceInitSetPowerPageable**](../wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowerpageable.md)

## -see-also

[*EvtDriverDeviceAdd*](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md)

[**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md)

