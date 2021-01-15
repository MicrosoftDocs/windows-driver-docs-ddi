---
UID: NS:ndis._PD_BUFFER
title: _PD_BUFFER (ndis.h)
description: This structure represents a PacketDirect (PD) packet, or a portion of a PD packet in a queue.
old-location: netvista\pd_buffer.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["PD_BUFFER structure"]
ms.keywords: PD_BUFFER, PD_BUFFER structure [Network Drivers Starting with Windows Vista], PPD_BUFFER, PPD_BUFFER structure pointer [Network Drivers Starting with Windows Vista], _PD_BUFFER, ndis/PD_BUFFER, ndis/PPD_BUFFER, netvista.pd_buffer
req.header: ndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.typenames: PD_BUFFER
f1_keywords:
 - _PD_BUFFER
 - ndis/_PD_BUFFER
 - PD_BUFFER
 - ndis/PD_BUFFER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ndis.h
api_name:
 - _PD_BUFFER
 - PD_BUFFER
---

# _PD_BUFFER structure


## -description

This structure represents a PacketDirect (PD) packet, or a portion of a PD packet in a queue.

## -struct-fields

### -field NextPDBuffer

A pointer to the next <b>PD_BUFFER</b> structure in the queue.

### -field NextPartialPDBuffer

A pointer to the next partial <b>PD_BUFFER</b> structure in the queue.

### -field PDClientReserved

Reserved for system use. Do not use.

### -field PDClientContext

The client and the provider are not allowed to modify this field.      If a client has allocated the <b>PD_BUFFER</b> with a non-zero value for      ClientContextSize, then the PDClientContext refers to a buffer size      of ClientContextSize. Otherwise, this field is NULL.

### -field DataBufferVirtualAddress

This field represents the address that hosts and software can use to access/modify the packet contents. The actual packet data is always at  DataBufferVirtualAddress+DataStart. The provider and the      platform never modify the value of this field after the <b>PD_BUFFER</b>      initialization.

### -field DataBufferDmaLogicalAddress

This field represents the logical memory location used for storing the packet data. The provider
must use for DMA. The actual packet data is always at
    DataBufferDmaLogicalAddress+DataStart. The provider and the
    platform must never modify the value of this field after the <b>PD_BUFFER</b>
    initialization.

### -field DataBufferSize

This is the total size of the allocated data buffer. The provider and the platform must never modify the value of this field
    after the <b>PD_BUFFER</b> initialization. This data type is <b>ULONG</b> instead of
    <b>USHORT</b> because of large send offload.

### -field PDClientContextSize

When this value is non-zero, it is the size of the buffer pointed to by PDClientContext.
    The value of this field must only be modified by the platform. The platform does not change the value of this field after the <b>PD_BUFFER</b> allocation.

### -field Attributes

The attributes must never be modified by the provider. The table below lists attributes that this <b>PD_BUFFER</b> structure can have.

<table>
<tr>
<th>Attribute</th>
<th>Description</th>
</tr>
<tr>
<td>PD_BUFFER_ATTR_BUILT_IN_DATA_BUFFER</td>
<td>A <b>PD_BUFFER</b> allocated with its own accompanying data buffer will have
this attribute set. The <b>PD_BUFFER</b> attributes must never be modified by clients
or providers.</td>
</tr>
</table>

### -field Flags

The following table lists flags that this <b>PD_BUFFER</b> structure can have.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>PD_BUFFER_FLAG_PARTIAL_PACKET_HEAD</td>
<td>Indicates that this buffer is the head of partial packets.</td>
</tr>
</table>

### -field DataStart

This field denotes where the packet starts relative to the original starting address of the allocated data buffer. The provider must never modify this field. The provider adds this value to the
    DataBufferDmaLogicalAddress value to derive the actual
    target DMA address for packet reception/transmission. For example, the
    target DMA address value in the hardware receive/transmit descriptor
    must be set to DataBufferDmaLogicalAddress+DataStart when a <b>PD_BUFFER</b>
    is posted to a receive/transmit queue.

### -field DataLength

The length of the this packet or partial packet data.

### -field MetaDataV0

### -field MetaDataV0.RxFilterContext

The provider sets this to the filter context value obtained
                from the matched filter that steered the packet to the receive
                queue. Filter context values are specified by the clients
                when configuring filters.

### -field MetaDataV0.GftFlowEntryId

If one of the RxGftExceptionPacket or RxGftCopyPacket or RxGftSamplePacket bits are set, the RxFilterContext value is
                overwritten with a GFT flow entry Id value.

### -field MetaDataV0.RxHashValue

The hash value computed for the incoming packet
            that is steered to the receive queue using RSS.

### -field MetaDataV0.RxIPHeaderChecksumSucceeded

A common RX offload field that indicates if the IP header checksum succeeded.

### -field MetaDataV0.RxTCPChecksumSucceeded

A common RX offload field that indicates if the TCP checksum succeeded.

### -field MetaDataV0.RxUDPChecksumSucceeded

A common RX offload field that indicates if the UDP checksum succeeded.

### -field MetaDataV0.RxIPHeaderChecksumFailed

A common RX offload field that indicates if the IP header checksum failed.

### -field MetaDataV0.RxTCPChecksumFailed

A common RX offload field that indicates if the TCP checksum failed.

### -field MetaDataV0.RxUDPChecksumFailed

A common RX offload field that indicates if the UDP checksum failed.

### -field MetaDataV0.RxHashComputed

A common RX offload field that indicates if the hash is computed.

### -field MetaDataV0.RxHashWithL4PortNumbers

A common RX offload field that indicates the hash is computed with L4 port numbers.

### -field MetaDataV0.RxGftDirectionIngress

### -field MetaDataV0.RxGftExceptionPacket

A common RX offload field that indicates this is a GFT exception packet.

### -field MetaDataV0.RxGftCopyPacket

A common RX offload field that indicates this is a GFT copy packet.

### -field MetaDataV0.RxGftSamplePacket

A common RX offload field that indicates this is a GFT sample packet.

### -field MetaDataV0.RxReserved1

Reserved.

### -field MetaDataV0.RxCoalescedSegCount

A common RX offload field that contains the amount of coalesced segments.

### -field MetaDataV0.RxRscTcpTimestampDelta

A common RX offload field that contains RSC and TCP timestamp difference.

### -field MetaDataV0.RxOffloads

RX offloads for this buffer.

### -field MetaDataV0.TxIsIPv4

A common TX offload field that indicates this packet is IPv4.

### -field MetaDataV0.TxIsIPv6

A common TX offload field that indicates this packet is IPv6.

### -field MetaDataV0.TxTransportHeaderOffset

A common TX offload field that contains the packet's header offset.

### -field MetaDataV0.TxMSS

A common TX offload field that contains the maximum segment size of this packet.

### -field MetaDataV0.TxComputeIPHeaderChecksum

A common TX offload field that indicates the IP header checksum is computed.

### -field MetaDataV0.TxComputeTCPChecksum

A common TX offload field that indicates the TCP checksum is computed.

### -field MetaDataV0.TxComputeUDPChecksum

A common TX offload field that indicates the UDP checksum is computed.

### -field MetaDataV0.TxIsEncapsulatedPacket

A common TX offload field that indicates the packet is encapsulated.

### -field MetaDataV0.TxInnerPacketOffsetsValid

A common TX offload field that indicates the inner packet offsets are valid.

### -field MetaDataV0.TxReserved1

Reserved.

### -field MetaDataV0.TxInnerFrameOffset

A common TX offload field that contains the inner frame offset.

### -field MetaDataV0.TxInnerIpHeaderRelativeOffset

A common TX offload field that contains the inner IP header relative offset.

### -field MetaDataV0.TxInnerIsIPv6

A common TX offload field that indicates the inner packet is IPv6.

### -field MetaDataV0.TxInnerTcpOptionsPresent

A common TX offload field that indicates the inner TCP options are present.

### -field MetaDataV0.TxOffloads

TX offloads for this buffer.

### -field MetaDataV0.VirtualSubnetInfo

The virtual subnet information.

### -field MetaDataV0.Ieee8021qInfo

The IEEE 802.1Q information.

### -field MetaDataV0.GftSourceVPortId

The GFT source virtual port ID.

### -field MetaDataV0.Reserved

Reserved for system use.

### -field MetaDataV0.ProviderScratch

A scratch field that the PD provider can use for its own purposes while the PD_BUFFER is sitting in the provider queue (in other words, posted by the client but not yet drained back by the client). Once the PD_BUFFER is drained by the client, there is no guarantee that the contents of this field will be preserved.

## -remarks

If an L2 packet is represented by multiple <b>PD_BUFFER</b> structures, the first <b>PD_BUFFER</b>
must have the PD_BUFFER_ATTR_BUILT_IN_DATA_BUFFER flag set and the
NextPartialPDBuffer field must point to the partial <b>PD_BUFFER</b> structures that
constitute the whole packet. Each of the partial <b>PD_BUFFER</b> structures must point to the next partial <b>PD_BUFFER</b> by using the NextPartialPDBuffer as opposed to the NextPDBuffer field. The NextPDBuffer field must be NULL in all partial <b>PD_BUFFER</b> structures except
for the head buffer. All partial PD_BUFFER structures except for the head buffer must
have the PD_BUFFER_ATTR_BUILT_IN_DATA_BUFFER flag cleared. The last partial
<b>PD_BUFFER</b> must have it's NextPartialPDBuffer field set to NULL. The total
length of the L2 packet is the sum of DataLength fields from each partial
<b>PD_BUFFER</b>. The head <b>PD_BUFFER</b> must contain up to and including the IP transport (TCP, UDP, SCTP, etc) header. In the case of encapsulation or double-encapsulation,
the inner-most IP transport header must be contained in the head <b>PD_BUFFER</b>.

When posting <b>PD_BUFFER</b> structures to receive queues, DataLength is ignored by
    the provider (For more information see the ReceiveDataLength description in the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_pd_queue_parameters">NDIS_PD_QUEUE_PARAMETERS</a> structure).
    When draining completed <b>PD_BUFFER</b>  structures from receive queues,
    the provider stores the length of the received packet in the  DataLength field. The length does not include FCS or any stripped 801Q
    headers.
    When posting <b>PD_BUFFER</b> structures to transmit queues, DataLength denotes the length
    of the packet to be sent. When draining completed <b>PD_BUFFER</b> structures from
    transmit queues, the provider leaves the DataLength field unmodified.

