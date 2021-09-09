---
UID: NF:wificx.WifiDeviceInitialize
tech.root: netvista
<<<<<<< HEAD
title: WifiDeviceInitialize (wificx.h)
ms.date: 08/18/2021
ms.topic: language-reference
targetos: Windows
description: The WifiDeviceInitialize function registers the client driver's WiFiCx-specific callback functions.
=======
title: WifiDeviceInitialize
ms.date: 04/30/2021
targetos: Windows
description: "Microsoft reserves the WifiDeviceInitialize function for internal use only. Don't use this function in your code."
>>>>>>> main
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wificx.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
<<<<<<< HEAD
req.target-min-winverclnt: Windows 11 
=======
req.target-min-winverclnt: Windows 11
>>>>>>> main
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificx.h
api_name:
 - WifiDeviceInitialize
f1_keywords:
 - WifiDeviceInitialize
 - wificx/WifiDeviceInitialize
dev_langs:
 - c++
---

## -description

The **WifiDeviceInitialize** function registers the client driver's WiFiCx-specific callback functions.

## -parameters

### -param Device

[_In_] A handle to a framework device object that the client driver obtained from a previous call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param Config

[_In_] A pointer to a client driver-allocated and initialized [**WIFI_DEVICE_CONFIG**](ns-wificx-wifi_device_config.md) structure.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, this function may return an appropriate NTSTATUS error code.

## -remarks

The client driver must call **WifiDeviceInitialize** from [*EVT_WDF_DRIVER_DEVICE_ADD*](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md), after calling [**NetDeviceInitConfig**](../netdevice/nf-netdevice-netdeviceinitconfig.md) but before calling [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

For an example of how to initialize a WifiCx device, see [Writing a WiFiCx client driver](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver).

## -see-also

[Writing a WiFiCx client driver](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver)

[**NetDeviceInitConfig**](../netdevice/nf-netdevice-netdeviceinitconfig.md)

[**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md)

[**WIFI_DEVICE_CONFIG**](ns-wificx-wifi_device_config.md)