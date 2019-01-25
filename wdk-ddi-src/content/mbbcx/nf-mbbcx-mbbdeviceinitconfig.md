---
UID: NF:mbbcx.MbbDeviceInitConfig
title: MbbDeviceInitConfig function (mbbcx.h)
description: The MBBDeviceInitConfig method initializes MBBCx device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.
tech.root: netvista
ms.assetid: c4998ab1-28f7-44d3-83ef-e6f303ff6279
ms.date: 06/28/2018
ms.topic: function
ms.keywords: MbbDeviceInitConfig
req.header: mbbcx.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver:
req.lib: mbbcxstub.lib
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
-	apiref
api_type: 
-	LibDef
api_location: 
-	mbbcxstub.lib
api_name: 
-	MbbDeviceInitConfig
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# MbbDeviceInitConfig function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
> 
> MBBCx is preview only in Windows 10, version 1809.

The **MBBDeviceInitConfig** method initializes MBBCx device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.

## -parameters

### -param DeviceInit

A pointer to a **WDFDEVICE_INIT** object that the client received in its [*EVT_WDF_DRIVER_DEVICE_ADD*](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) routine.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

## -remarks

The client driver calls this method in its [*EVT_WDF_DRIVER_DEVICE_ADD*](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) callback after it calls [**NetAdapterDeviceInitConfig**](../netadapter/nf-netadapter-netadapterdeviceinitconfig.md), but before it calls [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

For more information, see [Initialize the device](https://docs.microsoft.com/windows-hardware/drivers/netcx/writing-an-mbbcx-client-driver#initialize-the-device).

## -see-also
