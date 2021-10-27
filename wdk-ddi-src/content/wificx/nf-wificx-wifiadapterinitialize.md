---
UID: NF:wificx.WifiAdapterInitialize
tech.root: netvista
title: WifiAdapterInitialize (wificx.h)
ms.date: 08/23/2021
ms.topic: language-reference
targetos: Windows
description: The WifiAdapterInitialize function initializes a newly created NETADAPTER object for WiFiCx.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wificx.h
req.idl: 
req.include-header: 
req.irql: 
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
 - WifiAdapterInitialize
f1_keywords:
 - WifiAdapterInitialize
 - wificx/WifiAdapterInitialize
dev_langs:
 - c++
---

## -description

The **WifiAdapterInitialize** function initializes a newly created NETADAPTER object for WiFiCx.

## -parameters

### -param Adapter

[_In_] A handle to a NetAdapterCx NETADAPTER object obtained in a previous call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, this function may return an appropriate NTSTATUS error code.

This function might return failure in low resource situations.

## -remarks

The client driver must call this function from within [*EvtWifiDeviceCreateAdapter*](nc-wificx-evt_wifi_device_create_adapter.md). 

For more information, see [Writing a WiFiCx client driver](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver).

## -see-also

[**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md)

[*EvtWifiDeviceCreateAdapter*](nc-wificx-evt_wifi_device_create_adapter.md)

[Writing a WiFiCx client driver](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver)