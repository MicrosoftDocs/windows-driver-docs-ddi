---
UID: NF:wificx.WifiTxQueueGetDemuxWmmInfo
tech.root: netvista
<<<<<<< HEAD
title: WifiTxQueueGetDemuxWmmInfo (wificx.h)
ms.date: 08/31/2021
ms.topic: language-reference
targetos: Windows
description: The WifiTxQueueGetDemuxWmmInfo function gets the priority that the WiFiCx framework will use for this queue.
=======
title: WifiTxQueueGetDemuxWmmInfo
ms.date: 04/30/2021
targetos: Windows
description: "Microsoft reserves the WifiTxQueueGetDemuxWmmInfo function for internal use only. Don't use this function in your code."
>>>>>>> main
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
<<<<<<< HEAD
req.target-min-winverclnt: Windows 11 
=======
req.target-min-winverclnt: Windows 11
>>>>>>> main
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
 - WifiTxQueueGetDemuxWmmInfo
f1_keywords:
 - WifiTxQueueGetDemuxWmmInfo
 - wificx/WifiTxQueueGetDemuxWmmInfo
dev_langs:
 - c++
---

## -description

The **WifiTxQueueGetDemuxWmmInfo** function gets the priority that the WiFiCx framework will use for this queue.

## -parameters

### -param Queue

[_In_] A handle to this packet queue.

## -returns

Returns the queue priority. 

## -remarks

The client driver should query the queue priority from [*EvtPacketQueueStart*](/windows-hardware/drivers/ddi/netpacketqueue/nc-netpacketqueue-evt_packet_queue_start).

For more information, see [Setting up multiple Tx queues](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#setting-up-multiple-tx-queues).

## -see-also

[Setting up multiple Tx queues](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#setting-up-multiple-tx-queues)