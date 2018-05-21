---
UID: NE:netadapter._NET_ADAPTER_STATISTICS_FLAGS
title: _NET_ADAPTER_STATISTICS_FLAGS
author: windows-driver-content
description: Specifies statistics that an adapter supports.
ms.assetid: c20c2586-8d1d-484f-99ce-5eaf44f37886
ms.author: windowsdriverdev
ms.date: 02/05/2018
ms.topic: enum
ms.keywords: _NET_ADAPTER_STATISTICS_FLAGS, NET_ADAPTER_STATISTICS_FLAGS, 
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: netadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_ADAPTER_STATISTICS_FLAGS
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	NET_ADAPTER_STATISTICS_FLAGS
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# _NET_ADAPTER_STATISTICS_FLAGS enumeration

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Specifies statistics that an adapter supports.

## -enum-fields

### -field NET_ADAPTER_STATISTICS_NO_FLAGS : 
No flags are set.

### -field NET_ADAPTER_STATISTICS_XMIT_OK : 
The client can handle [OID_GEN_XMIT_OK](https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-xmit-ok).

### -field NET_ADAPTER_STATISTICS_RCV_OK : 
The client can handle [OID_GEN_RCV_OK](https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-rcv-ok).

### -field NET_ADAPTER_STATISTICS_XMIT_ERROR : 
The data in the **ifOutErrors** member of NDIS_STATISTICS_INFO is valid.

### -field NET_ADAPTER_STATISTICS_RCV_ERROR : 
The data in the **ifInErrors** member of NDIS_STATISTICS_INFO is valid.

### -field NET_ADAPTER_STATISTICS_RCV_NO_BUFFER : 
The client can handle [OID_GEN_RCV_NO_BUFFER](https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-rcv-no-buffer).

### -field NET_ADAPTER_STATISTICS_DIRECTED_BYTES_XMIT : 
The data in the **ifHCOutUcastOctets** member of NDIS_STATISTICS_INFO is valid.

### -field NET_ADAPTER_STATISTICS_DIRECTED_FRAMES_XMIT : 
The data in the **ifHCOutUcastPkts** member of NDIS_STATISTICS_INFO is valid.

### -field NET_ADAPTER_STATISTICS_MULTICAST_BYTES_XMIT : 
The data in the **ifHCOutMulticastOctets** member of NDIS_STATISTICS_INFO is valid.

### -field NET_ADAPTER_STATISTICS_MULTICAST_FRAMES_XMIT : 
The data in the **ifHCOutMulticastPkts** member of NDIS_STATISTICS_INFO is valid.

### -field NET_ADAPTER_STATISTICS_BROADCAST_BYTES_XMIT : 
The data in the **ifHCOutBroadcastOctets** member of NDIS_STATISTICS_INFO is valid.

### -field NET_ADAPTER_STATISTICS_BROADCAST_FRAMES_XMIT : 
The data in the **ifHCOutBroadcastPkts** member of NDIS_STATISTICS_INFO is valid.

### -field NET_ADAPTER_STATISTICS_DIRECTED_BYTES_RCV : 
The data in the **ifHCInUcastOctets** member of NDIS_STATISTICS_INFO is valid.

### -field NET_ADAPTER_STATISTICS_DIRECTED_FRAMES_RCV : 
The data in the **ifHCInUcastPkts** member is valid.

### -field NET_ADAPTER_STATISTICS_MULTICAST_BYTES_RCV : 
The data in the **ifHCInMulticastOctets** member of NDIS_STATISTICS_INFO is valid.

### -field NET_ADAPTER_STATISTICS_MULTICAST_FRAMES_RCV : 
The data in the **ifHCInMulticastPkts** member of NDIS_STATISTICS_INFO is valid.

### -field NET_ADAPTER_STATISTICS_BROADCAST_BYTES_RCV : 
The data in the **ifHCInBroadcastOctets** member of NDIS_STATISTICS_INFO is valid.

### -field NET_ADAPTER_STATISTICS_BROADCAST_FRAMES_RCV : 
The data in the **ifHCInBroadcastPkts** member of NDIS_STATISTICS_INFO is valid.

### -field NET_ADAPTER_STATISTICS_RCV_CRC_ERROR : 
The client can handle [OID_GEN_RCV_CRC_ERROR](https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-rcv-crc-error).

### -field NET_ADAPTER_STATISTICS_TRANSMIT_QUEUE_LENGTH : 
The client can handle [OID_GEN_TRANSMIT_QUEUE_LENGTH](https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-rcv-crc-error).

### -field NET_ADAPTER_STATISTICS_BYTES_RCV : 
The data in the **ifHCInOctets** member of NDIS_STATISTICS_INFO is valid.

### -field NET_ADAPTER_STATISTICS_BYTES_XMIT : 
The data in the **ifHCOutOctets** member of NDIS_STATISTICS_INFO is valid.

### -field NET_ADAPTER_STATISTICS_RCV_DISCARDS : 
The data in the **ifInDiscards** member of NDIS_STATISTICS_INFO is valid.

### -field NET_ADAPTER_STATISTICS_GEN_STATISTICS : 
The client can handle [OID_GEN_STATISTICS](https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-statistics).

### -field NET_ADAPTER_STATISTICS_XMIT_DISCARDS : 
The data in the **ifOutDiscards** member of NDIS_STATISTICS_INFO is valid.


## -remarks

The **NET_ADAPTER_STATISTICS_FLAGS** enumeration is used to specify supported statistics in the [NET_ADAPTER_LINK_LAYER_CAPABILITIES](ns-netadapter-_net_adapter_link_layer_capabilities.md) structure.

The client driver passes an initialized [NET_ADAPTER_LINK_LAYER_CAPABILITIES](ns-netadapter-_net_adapter_link_layer_capabilities.md) structure as an input parameter value to [NetAdapterSetLinkLayerCapabilities](nf-netadapter-netadaptersetlinklayercapabilities.md).

The client returns an NDIS_STATISTICS_INFO structure when handling an [OID_GEN_STATISTICS](https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-statistics) query.

The minimum NetAdapterCx version for **NET_ADAPTER_STATISTICS_FLAGS** is 1.0.

## -see-also

[NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES](../ndis/ns-ndis-_ndis_miniport_adapter_general_attributes.md)