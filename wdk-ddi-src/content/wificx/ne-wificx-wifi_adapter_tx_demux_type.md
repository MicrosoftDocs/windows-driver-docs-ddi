---
UID: NE:wificx._WIFI_ADAPTER_TX_DEMUX_TYPE
tech.root: netvista
<<<<<<< HEAD
title: WIFI_ADAPTER_TX_DEMUX_TYPE (wificx.h)
ms.date: 08/31/2021
ms.topic: language-reference
targetos: Windows
description: The WIFI_ADAPTER_TX_DEMUX_TYPE enumeration specifies the Tx DEMUX type. 
=======
title: WIFI_ADAPTER_TX_DEMUX_TYPE
ms.date: 04/30/2021
targetos: Windows
description: "Microsoft reserves the WIFI_ADAPTER_TX_DEMUX_TYPE enumeration for internal use only. Don't use this enumeration in your code."
>>>>>>> main
req.construct-type: enumeration
req.ddi-compliance: 
req.header: wificx.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
<<<<<<< HEAD
req.target-min-winverclnt: Windows 11 
=======
req.target-min-winverclnt: Windows 11
>>>>>>> main
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificx.h
api_name:
 - _WIFI_ADAPTER_TX_DEMUX_TYPE
 - WIFI_ADAPTER_TX_DEMUX_TYPE
f1_keywords:
 - _WIFI_ADAPTER_TX_DEMUX_TYPE
 - wificx/_WIFI_ADAPTER_TX_DEMUX_TYPE
 - WIFI_ADAPTER_TX_DEMUX_TYPE
 - wificx/WIFI_ADAPTER_TX_DEMUX_TYPE
dev_langs:
 - c++
---

## -description

The **WIFI_ADAPTER_TX_DEMUX_TYPE** enumeration specifies the Tx DEMUX type. 

## -enum-fields

### -field WifiAdapterTxDemuxTypePeerAddress:2

The type is PEER_ADDRESS.


### -field WifiAdapterTxDemuxTypeWmmInfo:3

The type is WWMINFO.

## -remarks

For more information, see [Setting up multiple Tx queues](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#setting-up-multiple-tx-queues).


## -see-also

[**WIFI_ADAPTER_TX_DEMUX**](ns-wificx-wifi_adapter_tx_demux.md)