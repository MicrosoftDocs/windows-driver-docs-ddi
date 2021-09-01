---
UID: NF:wificx.WifiAdapterGetType
tech.root: netvista
title: WifiAdapterGetType (wificx.h)
ms.date: 08/30/2021
ms.topic: language-reference
targetos: Windows
description: The WifiAdapterGetType function gets the Wi-Fi adapter type.
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
 - WifiAdapterGetType
f1_keywords:
 - WifiAdapterGetType
 - wificx/WifiAdapterGetType
dev_langs:
 - c++
---

## -description

Gets the Wi-Fi adapter type.

## -parameters

### -param Adapter

[_In_] A handle to a NETADAPTER object that the client driver obtained from a previous call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

## -returns

Returns a WIFI_ADAPTER_TYPE object that defines the Wi-Fi adapter type.

## -remarks

If the client driver needs to query the adapter type from the NETADAPTER_INIT object before the adapter is created, call [**WifiAdapterInitGetType**](nf-wificx-wifiadapterinitgettype.md) instead.

For a code example that uses **WifiAdapterGetType** during adapter creation, see [Event callback for adapter creation](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#event-callback-for-adapter-creation).

## -see-also

[**WifiAdapterInitGetType**](nf-wificx-wifiadapterinitgettype.md)