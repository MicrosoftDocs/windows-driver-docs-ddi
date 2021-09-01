---
UID: NS:wificx._WIFI_ADAPTER_TX_DEMUX
tech.root: netvista
title: WIFI_ADAPTER_TX_DEMUX (wificx.h)
ms.date: 08/31/2021
ms.topic: language-reference
targetos: Windows
description: The WIFI_ADAPTER_TX_DEMUX structure specifies Tx DEMUX information. 
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wificx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: WIFI_ADAPTER_TX_DEMUX
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificx.h
api_name:
 - _WIFI_ADAPTER_TX_DEMUX
 - WIFI_ADAPTER_TX_DEMUX
f1_keywords:
 - _WIFI_ADAPTER_TX_DEMUX
 - wificx/_WIFI_ADAPTER_TX_DEMUX
 - WIFI_ADAPTER_TX_DEMUX
 - wificx/WIFI_ADAPTER_TX_DEMUX
dev_langs:
 - c++
---

## -description

The **WIFI_ADAPTER_TX_DEMUX** structure specifies Tx DEMUX information. 

## -struct-fields

### -field Size

The size of this structure in bytes.

### -field Type

The demux type formatted as a [**WIFI_ADAPTER_TX_DEMUX_TYPE**](ne-wificx-wifi_adapter_tx_demux_type.md) enumeration.

### -field Range


## -remarks

For more information, see [Setting up multiple Tx queues](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#setting-up-multiple-tx-queues).

## -see-also

[**WIFI_ADAPTER_TX_DEMUX_TYPE**](ne-wificx-wifi_adapter_tx_demux_type.md)

[Setting up multiple Tx queues](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#setting-up-multiple-tx-queues)