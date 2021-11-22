---
UID: NF:wificx.WifiDeviceInitConfig
tech.root: netvista
title: WifiDeviceInitConfig (wificx.h)
ms.date: 08/12/2021
ms.topic: language-reference
targetos: Windows
description: The WifiDeviceInitConfig function initializes WiFiCx device initialization operations.
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
 - HeaderDef
api_location:
 - wificx.h
api_name:
 - WifiDeviceInitConfig
f1_keywords:
 - WifiDeviceInitConfig
 - wificx/WifiDeviceInitConfig
dev_langs:
 - c++
---

## -description

The **WifiDeviceInitConfig** function initializes WiFiCx device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.

## -parameters

### -param DeviceInit

[_Inout_] A pointer to a [**WDFDEVICE_INIT**](/windows-hardware/drivers/wdf/wdfdevice_init) object that the client driver received in its [*EVT_WDF_DRIVER_DEVICE_ADD*](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) routine.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, this function may return an appropriate NTSTATUS error code.

## -remarks

In its [*EVT_WDF_DRIVER_DEVICE_ADD*](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) callback function, a WifiCx client driver calls **WifiDeviceInitConfig** after calling [**NetDeviceInitConfig**](../netdevice/nf-netdevice-netdeviceinitconfig.md) but before calling [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

The driver must reference the same [**WDFDEVICE_INIT**](/windows-hardware/drivers/wdf/wdfdevice_init) object passed in by the framework.

## -see-also

[**WDFDEVICE_INIT**](/windows-hardware/drivers/wdf/wdfdevice_init)

[*EVT_WDF_DRIVER_DEVICE_ADD*](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) 

[**NetDeviceInitConfig**](../netdevice/nf-netdevice-netdeviceinitconfig.md)

[**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md)