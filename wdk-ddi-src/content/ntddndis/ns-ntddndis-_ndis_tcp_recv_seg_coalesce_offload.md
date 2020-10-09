---
UID: NS:ntddndis._NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD
title: _NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD (ntddndis.h)
description: The NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD structure contains the offload support state for receive segment coalescing (RSC).
old-location: netvista\ndis_tcp_recv_seg_coalesce_offload.htm
tech.root: netvista
ms.assetid: F474ABFA-D811-4C03-868A-E7C23BAE2017
ms.date: 05/02/2018
keywords: ["NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD structure"]
ms.keywords: "*PNDIS_TCP_RECV_SEG_COALESCE_OFFLOAD, NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD, NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD structure [Network Drivers Starting with Windows Vista], PNDIS_TCP_RECV_SEG_COALESCE_OFFLOAD, PNDIS_TCP_RECV_SEG_COALESCE_OFFLOAD structure pointer [Network Drivers Starting with Windows Vista], _NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD, netvista.ndis_tcp_recv_seg_coalesce_offload, ntddndis/NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD, ntddndis/PNDIS_TCP_RECV_SEG_COALESCE_OFFLOAD"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
req.typenames: NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD, *PNDIS_TCP_RECV_SEG_COALESCE_OFFLOAD
f1_keywords:
 - _NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD
 - ntddndis/_NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD
 - PNDIS_TCP_RECV_SEG_COALESCE_OFFLOAD
 - ntddndis/PNDIS_TCP_RECV_SEG_COALESCE_OFFLOAD
 - NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD
 - ntddndis/NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD
---

# _NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD structure


## -description

The <b>NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD</b>  structure contains the offload support state for receive segment coalescing (RSC).

## -struct-fields

### -field IPv4

### -field IPv4.Enabled

A BOOLEAN value that is set to TRUE if RSC processing on IPv4 traffic is supported. Otherwise, this member is FALSE.

### -field IPv6

### -field IPv6.Enabled

A BOOLEAN value that is set to TRUE if RSC processing on IPv6 traffic is supported. Otherwise, this member is FALSE.

## -remarks

A miniport driver advertises support for receive segment coalescing (RSC) in the Rsc member of the <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_offload">NDIS_OFFLOAD</a> structure that it passes to the <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a> function. 

The miniport driver can set the <b>IPv4.Enabled</b> member or the <b>IPv6.Enabled</b> member or both in the <b>NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD</b> structure to TRUE if it supports RSC for these protocols. The miniport driver must support RSC for 802.3 encapsulation or greater, and can support any other encapsulations. If the miniport driver does not support RSC for some encapsulation, the received packets of that encapsulation type must be indicated up the stack normally. 

To determine if a miniport driver supports RSC, NDIS drivers and other applications can query the  <a href="/windows-hardware/drivers/network/oid-tcp-connection-offload-hardware-capabilities">OID_TCP_OFFLOAD_HARDWARE_CAPABILITIES</a> OID which returns the NDIS_OFFLOAD structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_offload">NDIS_OFFLOAD</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>



<a href="/windows-hardware/drivers/network/oid-tcp-connection-offload-hardware-capabilities">OID_TCP_OFFLOAD_HARDWARE_CAPABILITIES</a>