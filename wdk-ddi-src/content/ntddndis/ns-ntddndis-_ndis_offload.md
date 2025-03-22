---
UID: NS:ntddndis._NDIS_OFFLOAD
title: _NDIS_OFFLOAD (ntddndis.h)
description: The NDIS_OFFLOAD structure specifies several computational tasks that can be offloaded to the network adapter.
old-location: netvista\ndis_offload.htm
tech.root: netvista
ms.date: 01/30/2024
ms.keywords: "*PNDIS_OFFLOAD, IPSEC_OFFLOAD_V2_AND_TCP_CHECKSUM_COEXISTENCE, IPSEC_OFFLOAD_V2_AND_UDP_CHECKSUM_COEXISTENCE, NDIS_OFFLOAD, NDIS_OFFLOAD structure [Network Drivers Starting with Windows Vista], PNDIS_OFFLOAD, PNDIS_OFFLOAD structure pointer [Network Drivers Starting with Windows Vista], _NDIS_OFFLOAD, netvista.ndis_offload, ntddndis/NDIS_OFFLOAD, ntddndis/PNDIS_OFFLOAD, tcpip_offload_ref_e5f796e9-714c-43f9-98e4-1d0de0dcc8ee.xml"
req.header: ntddndis.h
req.construct-type: structure
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista,Supported in NDIS 6.0 and later.
req.target-min-winversvr: Windows Server 2008
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
req.typenames: NDIS_OFFLOAD, *PNDIS_OFFLOAD
f1_keywords:
 - _NDIS_OFFLOAD
 - ntddndis/_NDIS_OFFLOAD
 - PNDIS_OFFLOAD
 - ntddndis/PNDIS_OFFLOAD
 - NDIS_OFFLOAD
 - ntddndis/NDIS_OFFLOAD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - _NDIS_OFFLOAD
 - PNDIS_OFFLOAD
 - NDIS_OFFLOAD
---

# NDIS_OFFLOAD structure (ntddndis.h)




## -description

The **NDIS_OFFLOAD** structure specifies several computational [tasks that can be offloaded to the network adapter](/windows-hardware/drivers/network/task-offload).

## -struct-fields

### -field Header

The [**NDIS_OBJECT_HEADER**](../objectheader/ns-objectheader-ndis_object_header.md) structure for the **NDIS_OFFLOAD** structure. Set the **Type** member of the structure that **Header** specifies to NDIS_OBJECT_TYPE_OFFLOAD.

Set the **Revision** and **Size** members of the [**NDIS_OBJECT_HEADER**](../objectheader/ns-objectheader-ndis_object_header.md) structure as follows:


- For NDIS 6.83 and later drivers:
  - Set **Revision** to NDIS_OFFLOAD_REVISION_6 (NDIS 6.83).
  - Set **Size** to NDIS_SIZEOF_NDIS_OFFLOAD_REVISION_6.
- For NDIS 6.70 and later drivers:
  - Set **Revision** to NDIS_OFFLOAD_REVISION_5 (NDIS 6.70).
  - Set **Size** to NDIS_SIZEOF_NDIS_OFFLOAD_REVISION_5.
- For NDIS 6.50 and later drivers:
  - Set **Revision** to NDIS_OFFLOAD_REVISION_4 (NDIS 6.50).
  - Set **Size** to NDIS_SIZEOF_NDIS_OFFLOAD_REVISION_4.
- For NDIS 6.30 and later drivers:
  - Set **Revision** to NDIS_OFFLOAD_REVISION_3 (NDIS 6.30).
  - Set **Size** to NDIS_SIZEOF_NDIS_OFFLOAD_REVISION_3.
- For NDIS 6.1 and 6.20 drivers:
  - Set **Revision** to NDIS_OFFLOAD_REVISION_2 (NDIS 6.1).
  - Set **Size** to NDIS_SIZEOF_NDIS_OFFLOAD_REVISION_2.
- For NDIS 6.0 drivers:
  - Set **Revision** to NDIS_OFFLOAD_REVISION_1 (NDIS 6.0).
  - Set **Size** to NDIS_SIZEOF_NDIS_OFFLOAD_REVISION_1.


### -field Checksum

Checksum offload information in an [**NDIS_TCP_IP_CHECKSUM_OFFLOAD**](/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_tcp_ip_checksum_offload) structure.

### -field LsoV1

Large send offload version 1 (LSOV1) information in an [**NDIS_TCP_LARGE_SEND_OFFLOAD_V1**](/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_tcp_large_send_offload_v1) structure.

### -field IPsecV1

Internet protocol security (IPsec) offload information in an [**NDIS_IPSEC_OFFLOAD_V1**](/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_ipsec_offload_v1) structure.

### -field LsoV2

Large send offload version 2 (LSOV2) offload information in an [**NDIS_TCP_LARGE_SEND_OFFLOAD_V2**](/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_tcp_large_send_offload_v2) structure.


### -field Flags

A bitwise OR  of flags that specify properties that the network adapter supports. The following flags are defined.

| Value | Meaning |
|-------|---------|
| **IPSEC_OFFLOAD_V2_AND_TCP_CHECKSUM_COEXISTENCE** <br> 0x00000002 | The network adapter supports IPsecV2 and TCP checksums. |
| **IPSEC_OFFLOAD_V2_AND_UDP_CHECKSUM_COEXISTENCE** <br> 0x00000004 | The network adapter supports IPsecV2 and UDP checksums. |

### -field IPsecV2

Internet protocol security (IPsec) offload version 2 information in an [**NDIS_IPSEC_OFFLOAD_V2**](/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_ipsec_offload_v2) structure.

### -field Rsc

[Receive Segment Coalescing (RSC)](/windows-hardware/drivers/network/receive-segment-coalescing--rsc-) offload information in an [**NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD**](/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_tcp_recv_seg_coalesce_offload) structure.

### -field EncapsulatedPacketTaskOffloadGre

[Network Virtualization using Generic Routing Encapsulation (NVGRE) Task Offload](/windows-hardware/drivers/network/network-virtualization-using-generic-routing-encapsulation--nvgre--task-offload) information in an <a href="/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_encapsulated_packet_task_offload">NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD</a> structure. This member should only be set by miniport drivers that support task offloads for NVGRE-formatted packets.

**Note**: This member is available only in NDIS 6.30 and later.

### -field EncapsulatedPacketTaskOffloadVxlan

VXLAN encapsulated packet task offload information in an [**NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_V2**](./ns-ntddndis-_ndis_encapsulated_packet_task_offload_v2.md) structure. This member should only be set by miniport drivers that support task offloads for VXLAN-formatted packets. VXLAN is similar to NVGRE, but with a different protocol.

**Note**: This member is available only in NDIS 6.50 and later.

### -field EncapsulationTypes

The enabled encapsulation types for encapsulated packet task offload.

**Note**:  This member is available only in NDIS 6.50 and later.

### -field Rfc6877Xlat

464XLAT hardware offload information in an [**NDIS_RFC6877_464XLAT_OFFLOAD**](./ns-ntddndis-_ndis_rfc6877_464xlat_offload.md) structure.

**Note**: This member is available only in NDIS 6.70 and later.

### -field UdpSegmentation

UDP Segmentation Offload (USO) hardware offload information in an [**NDIS_UDP_SEGMENTATION_OFFLOAD**](ns-ntddndis-_ndis_udp_segmentation_offload.md) structure.

**Note**: This member is available only in NDIS 6.83 and later. 

###  -field UdpRsc

UDP Receive Segment Coalescing Offload (URO) hardware offload information in an [**NDIS_UDP_RSC_OFFLOAD**](../nbluro/ns-nbluro-ndis_udp_rsc_offload.md) structure.

**Note**: This member is available only in NDIS 6.89 and later.

## -remarks

The **NDIS_OFFLOAD** structure is used in the following places:
- The **DefaultOffloadConfiguration** member of the [**NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES**](/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_offload_attributes) structure
- The **DefaultOffloadConfiguration** member of the [**NDIS_BIND_PARAMETERS**](/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_bind_parameters) structure
- The **DefaultOffloadConfiguration** member of the [**NDIS_FILTER_ATTACH_PARAMETERS**](/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_filter_attach_parameters) structure
- The **InformationBuffer** member of the [**NDIS_OID_REQUEST**](/windows-hardware/drivers/ddi/content/oidrequest/ns-oidrequest-ndis_oid_request) structure (which is used in the [OID_TCP_OFFLOAD_CURRENT_CONFIG](/windows-hardware/drivers/network/oid-tcp-offload-current-config) OID request)
- The **StatusBuffer** member of the [NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG](/windows-hardware/drivers/network/ndis-status-task-offload-current-config) status indication


## -see-also

[Determining the RSC Capabilities of a Network Adapter](/windows-hardware/drivers/network/determining-the-rsc-capabilities-of-a-network-adapter)

[**NDIS_BIND_PARAMETERS**](/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_bind_parameters)

[**NDIS_FILTER_ATTACH_PARAMETERS**](/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_filter_attach_parameters)

[**NDIS_IPSEC_OFFLOAD_V1**](/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_ipsec_offload_v1)

[**NDIS_IPSEC_OFFLOAD_V2**](/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_ipsec_offload_v2)

[**NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES**](/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_offload_attributes)

[**NDIS_OBJECT_HEADER**](/windows-hardware/drivers/ddi/content/objectheader/ns-objectheader-ndis_object_header)

[**NDIS_OID_REQUEST**](/windows-hardware/drivers/ddi/content/oidrequest/ns-oidrequest-ndis_oid_request)

[**NDIS_STATUS_INDICATION**](/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_status_indication)

[**NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG**](/windows-hardware/drivers/network/ndis-status-task-offload-current-config)

[**NDIS_TCP_IP_CHECKSUM_OFFLOAD**](/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_tcp_ip_checksum_offload)

[**NDIS_TCP_LARGE_SEND_OFFLOAD_V1**](/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_tcp_large_send_offload_v1)

[**NDIS_TCP_LARGE_SEND_OFFLOAD_V2**](/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_tcp_large_send_offload_v2)

[Network Virtualization using Generic Routing Encapsulation (NVGRE) Task Offload](/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_encapsulated_packet_task_offload)

[OID_OFFLOAD_ENCAPSULATION](/windows-hardware/drivers/network/oid-offload-encapsulation)

[OID_TCP_OFFLOAD_CURRENT_CONFIG](/windows-hardware/drivers/network/oid-tcp-offload-current-config)

[OID_TCP_OFFLOAD_HARDWARE_CAPABILITIES](/windows-hardware/drivers/network/oid-tcp-connection-offload-hardware-capabilities)

[TCP/IP Task Offload](/windows-hardware/drivers/network/task-offload)

[UDP Segmentation Offload (USO)](/windows-hardware/drivers/network/udp-segmentation-offload-uso-)

