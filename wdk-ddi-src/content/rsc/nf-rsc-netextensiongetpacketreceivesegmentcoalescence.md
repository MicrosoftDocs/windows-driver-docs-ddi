---
UID: NF:rsc.NetExtensionGetPacketReceiveSegmentCoalescence
title: NetExtensionGetPacketReceiveSegmentCoalescence function (rsc.h)
description: The NetExtensionGetPacketReceiveSegmentCoalescence method retrieves receive segment coalescence (RSC) information for a packet.
tech.root: netvista
ms.assetid: fad9b214-3c5b-445a-af85-2c9464dfa5f2
ms.date: 01/30/2019
ms.topic: function
f1_keywords:
 - "rsc/RILWRITEPHONEBOOKENTRYPARAMS"
ms.keywords: NetExtensionGetPacketReceiveSegmentCoalescence
req.header: rsc.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.29
req.umdf-ver:
req.lib:
req.dll:
req.irql: Any level as long as target memory is resident
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topictype: 
-	apiref
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	NetExtensionGetPacketReceiveSegmentCoalescence
product:
- Windows
targetos: Windows

---

# NetExtensionGetPacketReceiveSegmentCoalescence function


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NetExtensionGetPacketReceiveSegmentCoalescence** method retrieves receive segment coalescence (RSC) information for a packet.

## -parameters

### -param Extension

A pointer to a [**NET_EXTENSION**](../extension/ns-extension-_net_extension.md) structure that describes the RSC extension information for this receive queue. 

### -param Index

The index in the packet ring for the target [**NET_PACKET**](../packet/ns-packet-_net_packet.md).

## -returns

Returns a pointer to a [**NET_PACKET_RECEIVE_SEGMENT_COALESCENCE**](../rsctypes/ns-rsctypes-_net_packet_receive_segment_coalescence.md) structure that holds the RSC information for this packet.

## -remarks

NIC client drivers typically query offsets for packet extensions during datapath queue creation, then store them in their queue context space so they don't have to query them too often. For an example of this, see [Transmit and receive queues](https://docs.microsoft.com/windows-hardware/drivers/netcx/transmit-and-receive-queues). Clients can retrieve the RSC offset from the queue context to pass to **NetExtensionGetPacketReceiveSegmentCoalescence**.

This method is a wrapper method around [**NetExtensionGetData**](../extension/nf-extension-netextensiongetdata.md). 

## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[**NetExtensionGetData**](../extension/nf-extension-netextensiongetdata.md)
