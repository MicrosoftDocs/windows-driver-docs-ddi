---
UID: NF:fwpsk.FwpsConstructIpHeaderForTransportPacket0
title: FwpsConstructIpHeaderForTransportPacket0 function
author: windows-driver-content
description: The FwpsConstructIpHeaderForTransportPacket0 function is called by a callout to construct a new IP header or to rebuild a preexisting IP packet header for only one net buffer.Note  FwpsConstructIpHeaderForTransportPacket0 is a specific version of FwpsConstructIpHeaderForTransportPacket. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwpsconstructipheaderfortransportpacket0.htm
old-project: netvista
ms.assetid: badb7e91-1d5f-42c3-973b-c7d756d24a01
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: FwpsConstructIpHeaderForTransportPacket0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Server 2008.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FwpsConstructIpHeaderForTransportPacket0
req.alt-loc: fwpkclnt.lib,fwpkclnt.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsConstructIpHeaderForTransportPacket0 function



## -description
The 
  <b>FwpsConstructIpHeaderForTransportPacket0</b> function is called by a callout to construct a new IP header
  or to rebuild a preexisting IP packet header for only one net buffer.



## -syntax

````
NTSTATUS NTAPI FwpsConstructIpHeaderForTransportPacket0(
  _Inout_          NET_BUFFER_LIST *netBufferList,
  _In_             ULONG           headerIncludeHeaderSize,
  _In_             ADDRESS_FAMILY  addressFamily,
  _In_       const UCHAR           *sourceAddress,
  _In_       const UCHAR           *remoteAddress,
  _In_             IPPROTO         nextProtocol,
  _In_opt_         UINT64          endpointHandle,
  _In_opt_   const WSACMSGHDR      *controlData,
  _In_             ULONG           controlDataLength,
  _In_             UINT32          flags,
  _Reserved_       PVOID           reserved,
  _In_opt_         IF_INDEX        interfaceIndex,
  _In_opt_         IF_INDEX        subInterfaceIndex
);
````


## -parameters

### -param netBufferList [in, out]

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure that describes
     the cloned transport layer packet data for which a new IP header is to be constructed or rebuilt. To
     construct a new IP header, locate the offset of the cloned NET_BUFFER_LIST structure at the beginning of
     the transport header. To rebuild a preexisting IP packet header, locate the offset at the beginning of
     the IP header.


### -param headerIncludeHeaderSize [in]

If the NET_BUFFER_LIST structure pointed to by 
     <i>NetBufferList</i> already contains an IP header, indicates the total size, in bytes, of the existing
     IP header (if it exists). If 
     <i>NetBufferList</i> does not contain an IP header, 
     <i>headerIncludeHeaderSize</i> is zero. Otherwise, the value of this parameter is equal to the 
     <b>ipHeaderSize</b> member of the 
     <a href="..\fwpsk\ns-fwpsk-fwps_incoming_metadata_values0_.md">
     FWPS_INCOMING_METADATA_VALUES0</a> structure that is passed to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function. Note that
     extension headers for an existing IPv6 header will be removed when this function is called, although
     IPv4 options will be preserved. For more information, see Remarks.


### -param addressFamily [in]

One of the following address families:
     




### -param AF_INET

The IPv4 address family.


### -param AF_INET6

The IPv6 address family.

</dd>
</dl>

### -param sourceAddress [in]

A pointer to the source IP address that will be part of the IP header to be constructed. For IPv4,
     the address is 4 bytes. For IPv6, the address is 16 bytes. The source address bytes are always in
     network byte order.


### -param remoteAddress [in]

A pointer to a buffer that specifies the remote IP address that will be part of the IP header to
     be constructed.
     

The buffer can contain an IPv4 address (4 bytes) or an IPv6 address (16 bytes), and the address must
     be specified in network byte order. The IP version must match the 
     <i>addressFamily</i> parameter.


### -param nextProtocol [in]

Specifies the IPPROTO protocol type of the new IP header to be constructed. For more information
     on the IPPROTO enumeration, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff543744">AF_INET</a> or 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff543746">AF_INET6</a>.


### -param endpointHandle [in, optional]

An optional handle that indicates the stack transport endpoint in the send data path into which
     the packet is to be injected. This endpoint handle is provided to a callout through the 
     <b>transportEndpointHandle</b> member of the 
     <a href="..\fwpsk\ns-fwpsk-fwps_incoming_metadata_values0_.md">
     FWPS_INCOMING_METADATA_VALUES0</a> structure that is passed to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function.


### -param controlData [in, optional]

An optional pointer to a buffer that contains socket control data specified by the 
     <b>WSASendMsg</b> function, which is described in the Microsoft Windows SDK documentation. For
     information about the WSACMSGHDR type, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff544964">CMSGHDR</a>.
     

If present, socket control data is provided to a callout with the 
     <b>controlData</b> member of the 
     <a href="..\fwpsk\ns-fwpsk-fwps_incoming_metadata_values0_.md">
     FWPS_INCOMING_METADATA_VALUES0</a> structure that is passed to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function.

If socket control data is not <b>NULL</b>, it must be deep-copied in the callout driver's implementation of
     the 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> function, and the 
     <b>controlData</b> buffer must be kept valid until the injection completion function is
     called.


### -param controlDataLength [in]

The length, in bytes, of the 
     <i>controlData</i> parameter.


### -param flags [in]

Reserved. Callout drivers must set this parameter to zero.


### -param reserved 

Reserved. Callout drivers must set this parameter to <b>NULL</b>.


### -param interfaceIndex [in, optional]

The index of the interface on which the original packet data was received. A callout driver should use the value of the interface index that is passed as one of the incoming data values to its <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> callout function for this parameter. This parameter is optional and can be zero.


### -param subInterfaceIndex [in, optional]

The index of the subinterface on which the original packet data was received. A callout driver
     should use the value of the subinterface index that is passed as one of the incoming data values to its 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> callout function for this
     parameter if the packet is to be injected into the same subinterface where the original packet was
     indicated. This parameter is optional and can be zero.


## -returns
The 
     <b>FwpsConstructIpHeaderForTransportPacket0</b> function returns one of the following NTSTATUS
     codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>A new IP header was successfully constructed.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 


## -remarks
From a net buffer list cloned at a WFP outbound transport layer (FWPS_LAYER_OUTBOUND_TRANSPORT_Xxx), 
    <b>FwpsConstructIpHeaderForTransportPacket0</b> constructs a new header for each net buffer that is part
    of the net buffer list chain. This function can also be used to rebuild the preexisting IP header of a
    packet, in which case the net buffer list must contain only one net buffer.

This function is useful when the IP header has not yet been created, but the source IP address or the
    source port must be modified from the transport layer. Although it would ordinarily be possible to
    wait to perform such modifications until the packet reaches the Network layer, this cannot be done in an
    IPsec environment in which IP packets are encrypted or digitally signed before they reach the Network
    layer.

The source IP address can be modified to be another locally defined IP address or another address that
    does not exist on the local computer. Packets so modified can then be sent or injected into the receive
    or forwarding data path.

If a nonzero 
    <i>endpointHandle</i> parameter is specified, session states (socket options), if any, associated with the
    socket will be used to construct each new IP header. Similarly, if additional socket options are
    specified with the 
    <i>controlData</i> and 
    <i>controlDataLength</i> parameters, those options will be used to construct each new IP header.

If the input net buffer list was cloned from an inbound WFP transport layer, or if it was created as a
    result of a raw send operation, the net buffers will already contain an IP header. In this case, when
    this function is called, IPv4 options will be preserved in the new IP header, but AH/ESP headers and IPv6
    extension headers will be removed. Because the TCP/IP stack retains AH/ESP headers after IPsec
    processing, packets that have been indicated by WFP and cloned by callouts cannot readily be injected
    into the receive data path. Consequently this function is useful for rebuilding IPsec-processed packets
    that are to be injected into the receive data path with the 
    <a href="..\fwpsk\nf-fwpsk-fwpsinjecttransportreceiveasync0.md">FwpsInjectTransportReceiveAsync0</a> function.

For a header-include session; for example, to filter Generic Routing Encapsulation (GRE) traffic (IP
    protocol 47) sent on a raw socket from outbound transport layers, use the following procedure before you
    call 
    <b>FwpsConstructIpHeaderForTransportPacket0</b>:

Clone the net buffer list by calling the 
      <a href="..\fwpsk\nf-fwpsk-fwpsallocateclonenetbufferlist0.md">
      FwpsAllocateCloneNetBufferList0</a> function.

If the 
      <b>headerIncludeHeaderLength</b> member of the FWPS_INCOMING_METADATA_VALUES0 structure that is pointed
      to by the 
      <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> function's 
      <i>inMetaValues</i> parameter is greater than zero, retreat the cloned net buffer list by that amount; for example, by a call to 
      <a href="..\ndis\nf-ndis-ndisretreatnetbufferlistdatastart.md">NdisRetreatNetBufferListDataStart</a>.

Copy the buffer that is pointed to by the 
      <b>headerIncludeHeader</b> member of FWPS_INCOMING_METADATA_VALUES0 into the newly retreated region of
      the cloned net buffer list. The size of the buffer must be equal to the value of 
      <i>headerIncludeHeaderLength</i>.

Call 
      <b>FwpsConstructIpHeaderForTransportPacket0</b> that has the 
      <i>NetBufferList</i> parameter pointing to the cloned net buffer list and the 
      <i>headerIncludeHeaderSize</i> parameter set to the value of 
      <i>headerIncludeHeaderLength</i>.

<b>FwpsConstructIpHeaderForTransportPacket0</b> disables large send offload (LSO) and checksum offload
    support for the resulting net buffer list. Full checksums are calculated for upper-level protocols (TCP,
    UDP, and ICMP). The IP checksum is recalculated when the IP header is reconstructed.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543744">AF_INET</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543746">AF_INET6</a>
</dt>
<dt>
<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544964">CMSGHDR</a>
</dt>
<dt>
<a href="..\fwpsk\ns-fwpsk-fwps_incoming_metadata_values0_.md">
   FWPS_INCOMING_METADATA_VALUES0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsinjecttransportreceiveasync0.md">
   FwpsInjectTransportReceiveAsync0</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsConstructIpHeaderForTransportPacket0 function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

