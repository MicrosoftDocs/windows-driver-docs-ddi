---
UID: NS:extension._NET_EXTENSION
title: _NET_EXTENSION (extension.h)
description: The NET_EXTENSION structure describes the collection of net rings that belong to a packet queue.
tech.root: netvista
ms.assetid: 557978B2-EDEA-4C5B-87DB-9C62D2A177E4
ms.date: 02/06/2019
ms.topic: struct
ms.keywords: _NET_EXTENSION, NET_EXTENSION, *PNET_EXTENSION, 
req.header: extension.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.29
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_EXTENSION
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	extension.h
apiname: 
-	NET_EXTENSION
product:
-	Windows
targetos: Windows
product:
- Windows
---

# _NET_EXTENSION structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NET_EXTENSION** structure represents a packet extension for all packets in a packet queue.

## -struct-fields

### -field Reserved

Reserved. Client drivers must not read or write to this value.

### -field DUMMYUNIONNAME

A union that contains the **Enabled** and **Reserved1** members.

### -field DUMMYUNIONNAME.Enabled

A boolean value that indicates if this extension is currently enabled for the packets in this queue.

### field DUMMYUNIONNAME.Reserved1

Reserved. Client drivers must not read or write to this value.

## -remarks

Client drivers typically store packet extensions in the context space for each queue during queue creation, reducing calls out of the driver. Later, to retrieve packet extension information for a particular packet, the driver calls one of the wrapper methods around [**NetExtensionGetData**](../extension/nf-extension-netextensiongetdata.md). 

- For checksum offload information, the client driver calls [**NetExtensionGetPacketChecksum**](../checksum/nf-checksum-netextensiongetpacketchecksum.md).
- For Large Send Offload (LSO) information, the client driver calls [**NetExtensionGetPacketLargeSendSegmentation**](../lso/nf-lso-netextensiongetpacketlargesendsegmentation.md).
- For Receive Segment Coalescence (RSC) offload information, the client driver calls [**NetExtensionGetPacketReceiveSegmentCoalescence**](../rsc/nf-rsc-netextensiongetpacketreceivesegmentcoalescence.md).

For examples of creating packet queues, see [Transmit and receive queues](https://docs.microsoft.com/windows-hardware/drivers/netcx/transmit-and-receive-queues).

## -see-also

[Transmit and receive queues](https://docs.microsoft.com/windows-hardware/drivers/netcx/transmit-and-receive-queues)

[**NetExtensionGetPacketChecksum**](../checksum/nf-checksum-netextensiongetpacketchecksum.md)

[**NetExtensionGetPacketLargeSendSegmentation**](../lso/nf-lso-netextensiongetpacketlargesendsegmentation.md)

[**NetExtensionGetPacketReceiveSegmentCoalescence**](../rsc/nf-rsc-netextensiongetpacketreceivesegmentcoalescence.md)