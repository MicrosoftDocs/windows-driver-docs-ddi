---
UID: NS:wificx._WIFI_ADAPTER_TX_DEMUX
tech.root: netvista
<<<<<<< HEAD
title: WIFI_ADAPTER_TX_DEMUX (wificx.h)
ms.date: 08/31/2021
ms.topic: language-reference
targetos: Windows
description: The WIFI_ADAPTER_TX_DEMUX structure specifies Tx DEMUX information. 
=======
title: WIFI_ADAPTER_TX_DEMUX
ms.date: 04/30/2021
targetos: Windows
description: "Microsoft reserves the WIFI_ADAPTER_TX_DEMUX structure for internal use only. Don't use this structure in your code."
>>>>>>> main
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wificx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
<<<<<<< HEAD
req.target-min-winverclnt: Windows 11 
=======
req.target-min-winverclnt: Windows 11
>>>>>>> main
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

The maximum number of queues for QOS or peers.

## -remarks

If the demux type is WMMINFO call [**WIFI_ADAPTER_TX_WMMINFO_DEMUX_INIT**](nf-wificx-wifi_adapter_tx_wmminfo_demux_init.md) to initialize this structure. 

If the demux type is PEER_ADDRESS call [**WIFI_ADAPTER_TX_PEER_ADDRESS_DEMUX_INIT**](nf-wificx-wifi_adapter_tx_wmminfo_demux_init.md) to initialize this structure.

Call [**WifiAdapterInitAddTxDemux**](nf-wificx-wifiadapterinitaddtxdemux.md) to add the Tx demux information to the NETADAPTER.

For more information, see [Setting up multiple Tx queues](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#setting-up-multiple-tx-queues).

## -see-also

[**WIFI_ADAPTER_TX_DEMUX_TYPE**](ne-wificx-wifi_adapter_tx_demux_type.md)

[**WIFI_ADAPTER_TX_WMMINFO_DEMUX_INIT**](nf-wificx-wifi_adapter_tx_wmminfo_demux_init.md)

[**WIFI_ADAPTER_TX_PEER_ADDRESS_DEMUX_INIT**](nf-wificx-wifi_adapter_tx_peer_address_demux_init.md)

[**WifiAdapterInitAddTxDemux**](nf-wificx-wifiadapterinitaddtxdemux.md)

[Setting up multiple Tx queues](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#setting-up-multiple-tx-queues)