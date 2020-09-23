---
UID: NE:ntddndis._NDIS_RECEIVE_FILTER_TYPE
title: _NDIS_RECEIVE_FILTER_TYPE (ntddndis.h)
description: The NDIS_RECEIVE_FILTER_TYPE enumeration identifies the receive filter types that the miniport driver supports.
old-location: netvista\ndis_receive_filter_type.htm
tech.root: netvista
ms.assetid: 2810be51-4b38-4462-9c16-67a9f28da5c9
ms.date: 05/02/2018
keywords: ["NDIS_RECEIVE_FILTER_TYPE enumeration"]
ms.keywords: "*PNDIS_RECEIVE_FILTER_TYPE, NDIS_RECEIVE_FILTER_TYPE, NDIS_RECEIVE_FILTER_TYPE enumeration [Network Drivers Starting with Windows Vista], NdisReceiveFilterTypeMaximum, NdisReceiveFilterTypePacketCoalescing, NdisReceiveFilterTypeUndefined, NdisReceiveFilterTypeVMQueue, PNDIS_RECEIVE_FILTER_TYPE, PNDIS_RECEIVE_FILTER_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_FILTER_TYPE, netvista.ndis_receive_filter_type, ntddndis/NDIS_RECEIVE_FILTER_TYPE, ntddndis/NdisReceiveFilterTypeMaximum, ntddndis/NdisReceiveFilterTypePacketCoalescing, ntddndis/NdisReceiveFilterTypeUndefined, ntddndis/NdisReceiveFilterTypeVMQueue, ntddndis/PNDIS_RECEIVE_FILTER_TYPE, virtual_machine_queue_ref_8965d6c0-b700-46cd-9386-0e2cdc5da4c9.xml"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: NDIS_RECEIVE_FILTER_TYPE, *PNDIS_RECEIVE_FILTER_TYPE
f1_keywords:
 - _NDIS_RECEIVE_FILTER_TYPE
 - ntddndis/_NDIS_RECEIVE_FILTER_TYPE
 - PNDIS_RECEIVE_FILTER_TYPE
 - ntddndis/PNDIS_RECEIVE_FILTER_TYPE
 - NDIS_RECEIVE_FILTER_TYPE
 - ntddndis/NDIS_RECEIVE_FILTER_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_RECEIVE_FILTER_TYPE
---

# _NDIS_RECEIVE_FILTER_TYPE enumeration


## -description

The <b>NDIS_RECEIVE_FILTER_TYPE</b> enumeration identifies the receive filter types that the miniport driver
  supports.

## -enum-fields

### -field NdisReceiveFilterTypeUndefined

An undefined filter.

### -field NdisReceiveFilterTypeVMQueue

A filter for a virtual machine (VM) receive queue. This receive queue has been allocated by the miniport driver that supports the virtual machine queue (VMQ) or single root I/O virtualization (SR-IOV) interface.

### -field NdisReceiveFilterTypePacketCoalescing

A packet coalescing filter.

### -field NdisReceiveFilterTypeMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.

## -remarks

The NDIS_RECEIVE_FILTER_TYPE enumeration is used in the 
    <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_filter_parameters">
    NDIS_RECEIVE_FILTER_PARAMETERS</a> structure.

For more information about VMQ, see <a href="/windows-hardware/drivers/network/virtual-machine-queue--vmq-">Virtual Machine Queue (VMQ)</a>.

For more information about SR-IOV, see <a href="/windows-hardware/drivers/network/single-root-i-o-virtualization--sr-iov-">Single Root I/O Virtualization (SR-IOV)</a>.

For more information about packet coalescing, see <a href="/windows-hardware/drivers/network/ndis-packet-coalescing">NDIS Packet Coalescing</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_filter_parameters">
   NDIS_RECEIVE_FILTER_PARAMETERS</a>