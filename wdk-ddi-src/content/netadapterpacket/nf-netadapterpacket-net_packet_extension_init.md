---
UID: NF:netadapterpacket.NET_PACKET_EXTENSION_INIT
title: NET_PACKET_EXTENSION_INIT function
author: windows-driver-content
description: The NET_PACKET_EXTENSION_INIT method initializes a NET_PACKET_EXTENSION structure.
ms.assetid: 89f3058a-785e-4a01-8082-21851b77e8fd
ms.author: windowsdriverdev
ms.date: 03/01/2018
ms.topic: function
ms.keywords: NET_PACKET_EXTENSION_INIT
req.header: netadapterpacket.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib:NtosKrnl.exe
req.dll:
req.irql: PASSIVE_LEVEL
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
-	NET_PACKET_EXTENSION_INIT
product: Windows
targetos: Windows

---

# NET_PACKET_EXTENSION_INIT function


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The **NET_PACKET_EXTENSION_INIT** method initializes a [NET_PACKET_EXTENSION](ns-netadapterpacket-_net_packet_extension.md) structure.

## -parameters

### -param Extension
A pointer to the driver-allocated [NET_PACKET_EXTENSION](ns-netadapterpacket-_net_packet_extension.md) structure.

### -param Name
The name of the packet extension.

### -param Version
The version of the packet extension.

### -param ExtensionSize
The size of the packet extension, in bytes.

### -param Alignment
The alignment requirement for the extension.

## -returns
This method does not return a value.

## -remarks
For more information about packet extensions and available packet extension constants, see [Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions). For a code sample, see *[EvtNetAdapterCreateTxQueue](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)* or *[EvtNetAdapterCreateRxQueue](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)*.

The minimum NetAdapterCx version for **NET_PACKET_EXTENSION_INIT** is 1.2.

## -see-also