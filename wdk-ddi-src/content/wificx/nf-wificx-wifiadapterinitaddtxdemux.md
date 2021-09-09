---
UID: NF:wificx.WifiAdapterInitAddTxDemux
tech.root: netvista
title: WifiAdapterInitAddTxDemux (wificx.h)
ms.date: 08/31/2021
ms.topic: language-reference
targetos: Windows
description: The WifiAdapterInitAddTxDemux function adds DEMUX properties for multiple Tx queue support.
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
 - WifiAdapterInitAddTxDemux
f1_keywords:
 - WifiAdapterInitAddTxDemux
 - wificx/WifiAdapterInitAddTxDemux
dev_langs:
 - c++
---

## -description

The **WifiAdapterInitAddTxDemux** function adds DEMUX properties for multiple Tx queue support.

## -parameters

### -param Adapter

[_In_] A pointer to a NETADAPTER_INIT object that describes the initialization information for the NETADAPTER.

### -param Demux

[_In_] A pointer to an initialized [**WIFI_ADAPTER_TX_DEMUX**](ns-wificx-wifi_adapter_tx_demux.md) structure.

## -remarks

Before using a NETADAPTER_INIT object to create a NETADAPTER, client drivers add Tx DEMUX properties to the adapter.

For code examples see [Setting up multiple Tx queues](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#setting-up-multiple-tx-queues).

## -see-also

[Setting up multiple Tx queues](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#setting-up-multiple-tx-queues)

[**WIFI_ADAPTER_TX_DEMUX**](ns-wificx-wifi_adapter_tx_demux.md)