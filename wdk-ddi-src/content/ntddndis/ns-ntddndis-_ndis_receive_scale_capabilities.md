---
UID: NS:ntddndis._NDIS_RECEIVE_SCALE_CAPABILITIES
title: _NDIS_RECEIVE_SCALE_CAPABILITIES
author: windows-driver-content
description: The NDIS_RECEIVE_SCALE_CAPABILITIES structure specifies the receive side scaling (RSS) capabilities of a miniport adapter.
old-location: netvista\ndis_receive_scale_capabilities.htm
old-project: netvista
ms.assetid: dabd8f65-1aa5-4d45-9c0a-4539efd762c6
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_RECEIVE_SCALE_CAPABILITIES, *PNDIS_RECEIVE_SCALE_CAPABILITIES, NDIS_RECEIVE_SCALE_CAPABILITIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_RECEIVE_SCALE_CAPABILITIES
req.alt-loc: Ntddndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PNDIS_RECEIVE_SCALE_CAPABILITIES, NDIS_RECEIVE_SCALE_CAPABILITIES
---

# _NDIS_RECEIVE_SCALE_CAPABILITIES structure



## -description
The <b>NDIS_RECEIVE_SCALE_CAPABILITIES</b> structure specifies the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-receive-side-scaling2">receive side scaling (RSS)</a> capabilities of a miniport adapter. 
  
  



## -syntax

````
typedef struct _NDIS_RECEIVE_SCALE_CAPABILITIES {
  NDIS_OBJECT_HEADER  Header;
  NDIS_RSS_CAPS_FLAGS CapabilitiesFlags;
  ULONG               NumberOfInterruptMessages;
  ULONG               NumberOfReceiveQueues;
#if (NDIS_SUPPORT_NDIS630)
  USHORT              NumberOfIndirectionTableEntries;
#endif 
} NDIS_RECEIVE_SCALE_CAPABILITIES, *PNDIS_RECEIVE_SCALE_CAPABILITIES;
````


## -struct-fields

### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RECEIVE_SCALE_CAPABILITIES</b> structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_RSS_CAPABILITIES</b>. 

For NDIS 6.60 and later, set the 
     <b>Revision</b> member to <b>NDIS_RECEIVE_SCALE_CAPABILITIES_REVISION_3</b> and the 
     <b>Size</b> member to <b>NDIS_SIZEOF_RECEIVE_SCALE_CAPABILITIES_REVISION_3</b>.

For NDIS 6.30 and later, set the 
     <b>Revision</b> member to <b>NDIS_RECEIVE_SCALE_CAPABILITIES_REVISION_2</b> and the 
     <b>Size</b> member to <b>NDIS_SIZEOF_RECEIVE_SCALE_CAPABILITIES_REVISION_2</b>.

For NDIS 6.0, 6.1, and 6.20, set the 
     <b>Revision</b> member to <b>NDIS_RECEIVE_SCALE_CAPABILITIES_REVISION_1</b> and the 
     <b>Size</b> member to <b>NDIS_SIZEOF_RECEIVE_SCALE_CAPABILITIES_REVISION_1</b>.


### -field CapabilitiesFlags

A bitmask of flags that specify the RSS capabilities of the NIC. The
      miniport driver can specify the following flags:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field NDIS_RSS_CAPS_MESSAGE_SIGNALED_INTERRUPTS

</td>
<td width="60%">
Set this flag if the NIC supports message-signaled interrupts (MSIs). This flag indicates that
        the NIC can generate a separate interrupt for each CPU after it queues the packets that are assigned
        to that CPU.

</td>
</tr>
<tr>

### -field NDIS_RSS_CAPS_CLASSIFICATION_AT_ISR

</td>
<td width="60%">
Set this flag if the NIC can indicate to the <a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a> function which target CPUs have
        queued received packets.

</td>
</tr>
<tr>

### -field NDIS_RSS_CAPS_USING_MSI_X

</td>
<td width="60%">
Set this flag if the NIC is using message signaled interrupts (MSIs). This flag is supported in
       NDIS 6.20 and later.

</td>
</tr>
<tr>

### -field NDIS_RSS_CAPS_SUPPORTS_MSI_X

</td>
<td width="60%">
Set this flag if the NIC supports MSIs. This flag is supported in NDIS 6.30 and later.

</td>
</tr>
<tr>

### -field NDIS_RSS_CAPS_CLASSIFICATION_AT_DPC

</td>
<td width="60%">
Set this flag if the miniport driver can detect which target CPUs have queued receive packets
        from its <a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a> function.

</td>
</tr>
<tr>

### -field NDIS_RSS_CAPS_HASH_TYPE_TCP_IPV4

</td>
<td width="60%">
Set this flag if the NIC can identify an IPv4 packet (with or without options). Also, the NIC
        supports calculation of the hash value over the IPv4 header fields and TCP header fields.

</td>
</tr>
<tr>

### -field NDIS_RSS_CAPS_HASH_TYPE_TCP_IPV6

</td>
<td width="60%">
Set this flag if the NIC can identify an IPv6 packet and compute a hash value over fields in an
        IPv6 packet. The NIC must be able to compute a hash value over fields in the basic IPv6 header and
        over fields in the TCP header. Use this flag if the NIC cannot compute a hash value over fields that
        are located in IPv6 extension headers.

</td>
</tr>
<tr>

### -field NDIS_RSS_CAPS_HASH_TYPE_TCP_IPV6_EX

</td>
<td width="60%">
Set this flag if the NIC can identify an IPv6 packet and compute a hash value over fields in an
        IPv6 packet that contains IPv6 extension headers. The NIC can compute a hash value over fields in the
        basic IPv6 header, IPv6 extension headers, and TCP header. The NIC must be able to compute hash
        values over fields in the home address option and the type-2 routing header in the IPv6 extension
        headers.

</td>
</tr>
<tr>

### -field NDIS_RSS_CAPS_HASH_TYPE_UDP_IPV4

</td>
<td width="60%">
Set this flag if the NIC can identify an IPv4 packet, with or without options, and if the NIC supports calculation of the hash value over the IPv4 header fields and UDP header fields.

</td>
</tr>
<tr>

### -field NDIS_RSS_CAPS_HASH_TYPE_UDP_IPV6

</td>
<td width="60%">
Set this flag if the NIC can identify an IPv6 packet and compute a hash value over fields in an IPv6 packet. The NIC must be able to compute a hash value over fields in the basic IPv6 header and over fields in the UDP header. Use this flag if the NIC cannot compute a hash value over fields that are located in IPv6 extension headers.

</td>
</tr>
<tr>

### -field NDIS_RSS_CAPS_HASH_TYPE_UDP_IPV6_EX

</td>
<td width="60%">
Set this flag if the NIC can identify an IPv6 packet and compute a hash value over fields in an IPv6 packet that contains IPv6 extension headers. The NIC can compute a hash value over fields in the basic IPv6 header, IPv6 extension headers, and the UDP header. The NIC must be able to compute hash values over fields in the home address option and the type-2 routing header in the IPv6 extension headers. 

</td>
</tr>
<tr>

### -field NdisHashFunctionToeplitz

</td>
<td width="60%">
Set this flag if the NIC supports the toeplitz hash function. If the NIC supports RSS, support
        for the hash function is mandatory. For more information about hash functions, see
        <a href="https://msdn.microsoft.com/library/windows/hardware/ff567264">NDIS_RSS_HASH_FUNC_FROM_HASH_INFO</a>.

</td>
</tr>
<tr>

### -field NdisHashFunctionReserved1

</td>
<td width="60%">
This flag is reserved for future use.

</td>
</tr>
<tr>

### -field NdisHashFunctionReserved2

</td>
<td width="60%">
This flag is reserved for future use.

</td>
</tr>
<tr>

### -field NdisHashFunctionReserved3

</td>
<td width="60%">
This flag is reserved for future use.

</td>
</tr>
</table>
 


### -field NumberOfInterruptMessages

The number of interrupt messages that the NIC supports if the NIC supports MSIs. If the NIC does
     not support MSIs but supports line-based interrupts, set this number to 1.


### -field NumberOfReceiveQueues

The number of hardware receive queues that the NIC supports.


### -field NumberOfIndirectionTableEntries

The maximum number of entries that the miniport driver supports in the indirection table. This value must be a power of 2. All NDIS 6.30 and later miniport adapters must support this member, which is required for virtual functions.


## -remarks
Overlying drivers can use the 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-receive-scale-capabilities">
    OID_GEN_RECEIVE_SCALE_CAPABILITIES</a> OID to query the receive side scaling (RSS) capabilities of a
    NIC and its miniport driver.

The miniport driver returns the RSS capabilities in an <b>NDIS_RECEIVE_SCALE_CAPABILITIES</b> structure.

For some workloads, a subset of UDP packets could be fragmented due to route changes or the sender not adhering to MTU limitations. In such rare cases, packets of the same flow could be indicated on different processors based on the 4-tuple or 2-tuple hash. Therefore, miniport drivers that advertise <b>NDIS_RSS_CAPS_HASH_TYPE_UDP_IPV4</b>, <b>NDIS_RSS_CAPS_HASH_TYPE_UDP_IPV6</b>, and <b>NDIS_RSS_CAPS_HASH_TYPE_UDP_IPV6_EX</b> should provide a way to disable UDP RSS capabilities via Advanced Properties.


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndis_rss_hash_func_from_hash_info">
   NDIS_RSS_HASH_FUNC_FROM_HASH_INFO</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-receive-scale-capabilities">
   OID_GEN_RECEIVE_SCALE_CAPABILITIES</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-receive-side-scaling2">Receive Side Scaling (RSS)</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RECEIVE_SCALE_CAPABILITIES structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

