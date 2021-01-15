---
UID: NS:extension._NET_EXTENSION
title: _NET_EXTENSION (extension.h)
description: The NET_EXTENSION structure describes the collection of net rings that belong to a packet queue.
tech.root: netvista
ms.date: 02/06/2019
keywords: ["NET_EXTENSION structure"]
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
targetos: Windows
f1_keywords:
 - _NET_EXTENSION
 - extension/_NET_EXTENSION
 - NET_EXTENSION
 - extension/NET_EXTENSION
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - extension.h
api_name:
 - _NET_EXTENSION
 - NET_EXTENSION
---

# _NET_EXTENSION structure


## -description

The **NET_EXTENSION** structure represents a packet extension for all packets in a packet queue.

## -struct-fields

### -field Reserved

Reserved. Client drivers must not read or write to this value.

### -field DUMMYUNIONNAME

A union that contains the **Enabled** and **Reserved1** members.

### -field DUMMYUNIONNAME.Enabled

A boolean value that indicates if this extension is currently enabled for the packets in this queue.

### -field DUMMYUNIONNAME.Reserved1

Reserved. Client drivers must not read or write to this value.

## -remarks

Client drivers typically store packet extensions in the context space for each queue during queue creation, reducing calls out of the driver. Later, to retrieve packet extension information for a particular packet, the driver calls one of the wrapper functions around [**NetExtensionGetData**](../extension/nf-extension-netextensiongetdata.md). 

- For checksum offload information, the client driver calls [**NetExtensionGetPacketChecksum**](../checksum/nf-checksum-netextensiongetpacketchecksum.md).

For examples of creating packet queues, see [Transmit and receive queues](/windows-hardware/drivers/netcx/transmit-and-receive-queues).

## -see-also

[Transmit and receive queues](/windows-hardware/drivers/netcx/transmit-and-receive-queues)

[**NetExtensionGetPacketChecksum**](../checksum/nf-checksum-netextensiongetpacketchecksum.md)

