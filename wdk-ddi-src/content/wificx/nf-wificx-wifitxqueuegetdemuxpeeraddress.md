---
UID: NF:wificx.WifiTxQueueGetDemuxPeerAddress
tech.root: netvista
title: WifiTxQueueGetDemuxPeerAddress (wificx.h)
ms.date: 09/08/2021
ms.topic: language-reference
targetos: Windows
description: The WifiTxQueueGetDemuxPeerAddress function gets the peer address that the WiFiCx framework will use for this queue.
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
 - WifiTxQueueGetDemuxPeerAddress
f1_keywords:
 - WifiTxQueueGetDemuxPeerAddress
 - wificx/WifiTxQueueGetDemuxPeerAddress
dev_langs:
 - c++
---

## -description

The **WifiTxQueueGetDemuxPeerAddress** function gets the peer address that the WiFiCx framework will use for this queue.

## -parameters

### -param Queue

[_In_] A handle to this packet queue.

## -returns

Returns the peer address.

## -remarks

The client driver should query the peer address from [*EvtPacketQueueStart*](/windows-hardware/drivers/ddi/netpacketqueue/nc-netpacketqueue-evt_packet_queue_start).

For more information, see [Setting up multiple Tx queues](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#setting-up-multiple-tx-queues).

## -see-also

[Setting up multiple Tx queues](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#setting-up-multiple-tx-queues)

