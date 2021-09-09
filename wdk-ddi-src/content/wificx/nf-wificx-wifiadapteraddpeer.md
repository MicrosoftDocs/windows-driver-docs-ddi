---
UID: NF:wificx.WifiAdapterAddPeer
tech.root: netvista
title: WifiAdapterAddPeer (wificx.h)
ms.date: 09/07/2021
ms.topic: language-reference
targetos: Windows
description: Client drivers call WifiAdapterAddPeer to tell the WiFiCx framework that a peer has connected with the given address.
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
 - WifiAdapterAddPeer
f1_keywords:
 - WifiAdapterAddPeer
 - wificx/WifiAdapterAddPeer
dev_langs:
 - c++
---

## -description

Client drivers call the **WifiAdapterAddPeer** function to tell the WiFiCx framework that a peer has connected with the given address. WiFiCx will associate a queue to the peer address. 

## -parameters

### -param Adapter

[_In_] A handle to a NetAdapterCx NETADAPTER object obtained in a previous call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

### -param Address

The peer address.

## -remarks

The maximum number of peers that the driver may add shall not exceed the range value provided when adding Tx demultiplexing info.

For more information see [Setting up multiple Tx queues](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#setting-up-multiple-tx-queues).

## -see-also

[**WifiAdapterRemovePeer**](nf-wificx-wifiadapterremovepeer.md)

[**WifiAdapterInitAddTxDemux**](nf-wificx-wifiadapterinitaddtxdemux.md)


[Setting up multiple Tx queues](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#setting-up-multiple-tx-queues)