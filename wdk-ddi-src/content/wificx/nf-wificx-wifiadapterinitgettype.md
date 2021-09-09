---
UID: NF:wificx.WifiAdapterInitGetType
tech.root: netvista
title: WifiAdapterInitGetType (wificx.h)
ms.date: 08/30/2021
ms.topic: language-reference
targetos: Windows
description: The WifiAdapterInitGetType function gets the adapter type from the NETADAPTER_INIT object.
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
 - WifiAdapterInitGetType
f1_keywords:
 - WifiAdapterInitGetType
 - wificx/WifiAdapterInitGetType
dev_langs:
 - c++
---

## -description

A WiFiCx client driver calls the **WifiAdapterInitGetType** function when it needs to query the adapter type from the NETADAPTER_INIT object before the adapter is created.

## -parameters

### -param AdapterInit

[_In_] A pointer to a caller-provided NETADAPTER_INIT object.

## -returns

Returns a WIFI_ADAPTER_TYPE object that defines the Wi-Fi adapter type.

## -remarks

## -see-also

[**WifiAdapterGetType**](nf-wificx-wifiadaptergettype.md)