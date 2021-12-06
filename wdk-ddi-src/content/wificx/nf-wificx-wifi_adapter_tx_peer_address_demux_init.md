---
UID: NF:wificx.WIFI_ADAPTER_TX_PEER_ADDRESS_DEMUX_INIT
tech.root: netvista
title: WIFI_ADAPTER_TX_PEER_ADDRESS_DEMUX_INIT (wificx.h)
ms.date: 09/08/2021
ms.topic: language-reference
targetos: Windows
description: WIFI_ADAPTER_TX_PEER_ADDRESS_DEMUX_INIT initializes a WIFI_ADAPTER_TX_DEMUX structure when the Tx DEMUX type is PEER_ADDRESS.
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
 - WIFI_ADAPTER_TX_PEER_ADDRESS_DEMUX_INIT
f1_keywords:
 - WIFI_ADAPTER_TX_PEER_ADDRESS_DEMUX_INIT
 - wificx/WIFI_ADAPTER_TX_PEER_ADDRESS_DEMUX_INIT
dev_langs:
 - c++
---

## -description

The **WIFI_ADAPTER_TX_PEER_ADDRESS_DEMUX_INIT** function initializes a [**WIFI_ADAPTER_TX_DEMUX**](ns-wificx-wifi_adapter_tx_demux.md) structure when the Tx DEMUX type is PEER_ADDRESS.

## -parameters

### -param Demux

[_Out_] A pointer to the [**WIFI_ADAPTER_TX_DEMUX**](ns-wificx-wifi_adapter_tx_demux.md) structure.

### -param Range

[_In_] The maximum number of peers.

## -remarks

For more information, see [Setting up multiple Tx queues](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#setting-up-multiple-tx-queues).

## -see-also

[**WIFI_ADAPTER_TX_DEMUX**](ns-wificx-wifi_adapter_tx_demux.md)

[Setting up multiple Tx queues](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#setting-up-multiple-tx-queues)