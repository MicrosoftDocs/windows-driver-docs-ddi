---
UID: NF:packet.NetPacketGetExtension
title: NetPacketGetExtension function (packet.h)
description: The NetPacketGetExtension function retrieves information stored in one of a packet's extensions.
tech.root: netvista
ms.date: 01/30/2019
keywords: ["NetPacketGetExtension function"]
ms.keywords: NetPacketGetExtension
req.header: packet.h
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
targetos: Windows
f1_keywords:
 - NetPacketGetExtension
 - packet/NetPacketGetExtension
topictype:
 - apiref
apitype:
 - DllExport
apilocation:
 - NtosKrnl.exe
apiname:
 - NetPacketGetExtension
---

# NetPacketGetExtension function


## -description

The **NetPacketGetExtension** function retrieves information stored in one of a packet's extensions.

## -parameters

### -param packet

A pointer to a [**NET_PACKET**](ns-packet-_net_packet.md) structure.

### -param offset

The offset, in bytes, to the desired [**NET_EXTENSION**](../extension/ns-extension-_net_extension.md) from the beginning of the packet's descriptor.

## -returns

Returns a pointer to a structure at the given extension offset that represents packet extension information.

## -remarks

NIC client drivers typically query offsets for packet extensions during datapath queue creation, then store them in their queue context space so they don't have to query them too often. For an example of this, see [Transmit and receive queues](/windows-hardware/drivers/netcx/transmit-and-receive-queues). These offsets are then passed to **NetPacketGetExtension** to retrieve data for each packet extension.

## -see-also

[Packet descriptors and extensions](/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[Transmit and receive queues](/windows-hardware/drivers/netcx/transmit-and-receive-queues)
