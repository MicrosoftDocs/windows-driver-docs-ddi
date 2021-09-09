---
UID: NF:wificx.WIFI_ADAPTER_TX_WMMINFO_DEMUX_INIT
tech.root: netvista
title: WIFI_ADAPTER_TX_WMMINFO_DEMUX_INIT (wificx.h)
ms.date: 08/31/2021
ms.topic: language-reference
targetos: Windows
description: The WIFI_ADAPTER_TX_WMMINFO_DEMUX_INIT function initializes a WIFI_ADAPTER_TX_DEMUX structure when the Tx DEMUX type is WMMINFO.
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
 - WIFI_ADAPTER_TX_WMMINFO_DEMUX_INIT
f1_keywords:
 - WIFI_ADAPTER_TX_WMMINFO_DEMUX_INIT
 - wificx/WIFI_ADAPTER_TX_WMMINFO_DEMUX_INIT
dev_langs:
 - c++
---

## -description

The **WIFI_ADAPTER_TX_WMMINFO_DEMUX_INIT** function initializes a [**WIFI_ADAPTER_TX_DEMUX**](ns-wificx-wifi_adapter_tx_demux.md) structure when the Tx DEMUX type is WMMINFO.

## -parameters

### -param Demux

[_Out_] A pointer to the [**WIFI_ADAPTER_TX_DEMUX**](ns-wificx-wifi_adapter_tx_demux.md) structure.

## -remarks

For more information, see [Setting up multiple Tx queues](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#setting-up-multiple-tx-queues).

## -see-also

[Setting up multiple Tx queues](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#setting-up-multiple-tx-queues)

[**WIFI_ADAPTER_TX_DEMUX**](ns-wificx-wifi_adapter_tx_demux.md)