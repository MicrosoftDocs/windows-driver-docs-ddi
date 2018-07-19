---
UID: NF:netdevice.NetDeviceOpenConfiguration
title: NetDeviceOpenConfiguration function
author: windows-driver-content
description: The NetDeviceOpenConfiguration method opens a net device's configuration database.
ms.assetid: 3446a849-1637-4aa8-96b6-70491c47bf31
ms.author: windowsdriverdev
ms.date: 07/19/2018
ms.topic: function
ms.keywords: NetDeviceOpenConfiguration
req.header: netdevice.h
req.include-header: netadaptercxstub.lib
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
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
topic_type: 
-	apiref
api_type: 
-	LibDef
api_location: 
-	netadaptercxstub.lib
api_name: 
-	NetDeviceOpenConfiguration
product: Windows
targetos: Windows


---

# NetDeviceOpenConfiguration function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NetDeviceOpenConfiguration** method opens a net device's configuration database.

## -parameters

### -param Device

The WDFDEVICE object the client driver previously created with a call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param ConfigurationAttributes

A pointer to a [**WDF_OBJECT_ATTRIBUTES**](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure that contains driver-supplied attributes for the new configuration object. This parameter is optional and can be **WDF_NO_OBJECT_ATTRIBUTES**.

### -param Configuration

A pointer to the location that receives the new NETCONFIGURATION object.

## -returns

This method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

## -remarks

Typically, the client calls this method from its [*EVT_WDF_DRIVER_DEVICE_ADD*](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) callback function.

If the client provides a [**WDF_OBJECT_ATTRIBUTES**](../wdfobject/ns-wdfobject-_wdf_object_attributes.md), it specifies **NULL** for **ParentObject**. The device configuration object is automatically parented to the device object.

As a result, WDF automatically deletes the configuration object when the device is deleted. However, the client can manually delete a configuration object by calling [**WdfObjectDelete**](../wdfobject/nf-wdfobject-wdfobjectdelete.md), typically from its [*EVT_WDF_OBJECT_CONTEXT_CLEANUP*](../wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup.md) callback function.

## -see-also

[Accessing configuration information](https://docs.microsoft.com/windows-hardware/drivers/netcx/accessing-configuration-information)