---
UID: NC:wificx.EVT_WIFI_DEVICE_CREATE_ADAPTER
tech.root: netvista
title: EVT_WIFI_DEVICE_CREATE_ADAPTER (wificx.h)
ms.date: 08/23/2021
ms.topic: language-reference
targetos: Windows
description: WiFiCx drivers implement EvtWifiDeviceCreateAdapter to create a NETADAPTER object.
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
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - wificx.h
api_name:
 - EVT_WIFI_DEVICE_CREATE_ADAPTER
f1_keywords:
 - EVT_WIFI_DEVICE_CREATE_ADAPTER
 - wificx/EVT_WIFI_DEVICE_CREATE_ADAPTER
dev_langs:
 - c++
---

## -description

WiFiCx client drivers implement *EvtWifiDeviceCreateAdapter* to create a NETADAPTER object.

## -parameters

### -param Device

[_In_] A handle to a framework device object that the client driver obtained from a previous call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param AdapterInit

[_Inout_] A pointer to a NETADAPTER_INIT object that describes the initialization information for the NETADAPTER.

## -returns

This callback function returns STATUS_SUCCESS if the operation was successful. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

A WiFiCx client driver must register an *EvtWifiDeviceCreateAdapter* callback function by calling [**WiFiDeviceInitialize**](nf-wificx-wifideviceinitialize.md).

In its *EvtWifiDeviceCreateAdapter* callback, the client driver must:

1. Call [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md) to create the new NetAdapter object.

2. Call [**WifiAdapterInitialize**](nf-wificx-wifiadapterinitialize.md) to initialize the WiFiCx context and associate it with this NetAdapter object.

3. Call [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md) to start the adapter.

For more information, see [Writing a WiFiCx client driver](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver).

## -see-also

[**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md)

[**WiFiDeviceInitialize**](nf-wificx-wifideviceinitialize.md)

[**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md)

[**WifiAdapterInitialize**](nf-wificx-wifiadapterinitialize.md)

[**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md)

[Writing a WiFiCx client driver](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver)
