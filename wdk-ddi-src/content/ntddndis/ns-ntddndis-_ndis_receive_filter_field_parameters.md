---
UID: NS:ntddndis._NDIS_RECEIVE_FILTER_FIELD_PARAMETERS
title: "_NDIS_RECEIVE_FILTER_FIELD_PARAMETERS"
author: windows-driver-content
description: The NDIS_RECEIVE_FILTER_FIELD_PARAMETERS structure specifies the filter test criterion for a field in a network packet header.
old-location: netvista\ndis_receive_filter_field_parameters.htm
old-project: netvista
ms.assetid: 3d387fe9-a7cc-4034-b31e-ba1359db2ae1
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_RECEIVE_FILTER_FIELD_PARAMETERS, NDIS_RECEIVE_FILTER_FIELD_MAC_HEADER_VLAN_UNTAGGED_OR_ZERO, NDIS_RECEIVE_FILTER_FIELD_PARAMETERS, NDIS_RECEIVE_FILTER_FIELD_PARAMETERS structure [Network Drivers Starting with Windows Vista], NDIS_RECEIVE_FILTER_FIELD_PARAMETERS_REVISION_1, NDIS_RECEIVE_FILTER_FIELD_PARAMETERS_REVISION_2, PNDIS_RECEIVE_FILTER_FIELD_PARAMETERS, PNDIS_RECEIVE_FILTER_FIELD_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_FILTER_FIELD_PARAMETERS, netvista.ndis_receive_filter_field_parameters, ntddndis/NDIS_RECEIVE_FILTER_FIELD_PARAMETERS, ntddndis/PNDIS_RECEIVE_FILTER_FIELD_PARAMETERS, virtual_machine_queue_ref_deaf4f73-294d-4e7b-8c94-65d05b461cfe.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_RECEIVE_FILTER_FIELD_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_RECEIVE_FILTER_FIELD_PARAMETERS, *PNDIS_RECEIVE_FILTER_FIELD_PARAMETERS
---

# _NDIS_RECEIVE_FILTER_FIELD_PARAMETERS structure


## -description


The <b>NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</b> structure specifies the filter test criterion for a field
  in a network packet header.

NDIS receive filters are used in the following NDIS interfaces:
<ul>
<li>

<a href="https://msdn.microsoft.com/500FBF0F-54D9-4675-8E2D-447387DA8798">NDIS Packet Coalescing</a>. For more information about how to use receive filters in this interface, see <a href="https://msdn.microsoft.com/20EA71E0-B880-4891-A12E-76F4C9AB16E6">Managing Packet Coalescing Receive Filters</a>.

</li>
<li>

<a href="https://msdn.microsoft.com/E64DD4F0-D5F8-4FFF-931B-C04C5C42D000">Single Root I/O Virtualization (SR-IOV)</a>. For more information about how to use receive filters in this interface, see <a href="https://msdn.microsoft.com/F0137D59-1701-4DFC-BB30-27E477FC0706">Setting a Receive Filter on a Virtual Port</a>.

</li>
<li>

<a href="https://msdn.microsoft.com/c502c7d6-bdf1-4656-b5a5-339250910f08">Virtual Machine Queue (VMQ)</a>. For more information about how to use receive filters in this interface, see <a href="https://msdn.microsoft.com/bfee8a3c-d2be-4718-beb4-067b66756a41">Setting and Clearing VMQ Filters</a>.

</li>
</ul>

## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</b> structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT.

To indicate the version of the <b>NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</b> structure, the driver sets the 
     <b>Revision</b> member to one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDIS_RECEIVE_FILTER_FIELD_PARAMETERS_REVISION_2"></a><a id="ndis_receive_filter_field_parameters_revision_2"></a><dl>
<dt><b>NDIS_RECEIVE_FILTER_FIELD_PARAMETERS_REVISION_2</b></dt>
<dt>2</dt>
</dl>
</td>
<td width="60%">
Added additional members to the <b>HeaderField</b> union for NDIS 6.30.

The driver sets the 
        <b>Size</b> member to <b>NDIS_SIZEOF_RECEIVE_FILTER_FIELD_PARAMETERS_REVISION_2</b>.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_RECEIVE_FILTER_FIELD_PARAMETERS_REVISION_1"></a><a id="ndis_receive_filter_field_parameters_revision_1"></a><dl>
<dt><b>NDIS_RECEIVE_FILTER_FIELD_PARAMETERS_REVISION_1</b></dt>
<dt>1</dt>
</dl>
</td>
<td width="60%">
Original version for NDIS 6.20.

The driver sets the 
        <b>Size</b> member to <b>NDIS_SIZEOF_RECEIVE_FILTER_FIELD_PARAMETERS_REVISION_1</b>.

</td>
</tr>
</table>
 


### -field Flags

A bitwise OR of flags. The following flags are valid for the 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-set-filter">
     OID_RECEIVE_FILTER_SET_FILTER</a> OID.
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDIS_RECEIVE_FILTER_FIELD_MAC_HEADER_VLAN_UNTAGGED_OR_ZERO"></a><a id="ndis_receive_filter_field_mac_header_vlan_untagged_or_zero"></a><dl>
<dt><b>NDIS_RECEIVE_FILTER_FIELD_MAC_HEADER_VLAN_UNTAGGED_OR_ZERO</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%">
If this flag is set, the network adapter must only indicate received packets that pass the following criteria:

<ul>
<li>
The packet's media access control (MAC) address matches the specified MAC header field test.

</li>
<li>
The packet either does not contain a VLAN tag or has a VLAN tag with an ID of zero. 

</li>
</ul>
For more information about this flag, see the Remarks section.

<div class="alert"><b>Note</b>  If an overlying driver sets a MAC address filter and a VLAN identifier filter with an
       OID request of <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-set-filter">OID_RECEIVE_FILTER_SET_FILTER</a>, it does not set this flag in either of the filter fields. In this
       case, the miniport driver should indicate packets that match both the specified MAC address and the
       VLAN identifier. That is, the miniport driver should not indicate packets with a matching MAC address
       that have a zero VLAN identifier or are untagged packets.</div>
<div> </div>
</td>
</tr>
</table>
 


### -field FrameHeader

The type of header in the network data frame.


### -field ReceiveFilterTest

The type of test to perform for the receive filter.


### -field HeaderField

The type of field in a header. The field type (for example,
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff565889">NDIS_MAC_HEADER_FIELD</a>) corresponds to the type of header that is specified in the 
     <b>FrameHeader</b> member.
     

This union contains the following members:



#### MacHeaderField

The type of field in a MAC header.



#### ArpHeaderField

The type of field in an Address Resolution Protocol (ARP) header.



#### IPv4HeaderField

An 
       <a href="https://msdn.microsoft.com/library/windows/hardware/hh451553">NDIS_IPV4_HEADER_FIELD</a> enumeration
       value that specifies the type of field in an IP version 4 (IPv4) header.



#### IPv6HeaderField

An 
       <a href="https://msdn.microsoft.com/library/windows/hardware/hh451554">NDIS_IPV6_HEADER_FIELD</a> enumeration
       value that specifies the type of field in an IP version 6 (IPv6) header.



#### UdpHeaderField

The type of field in a User Datagram Protocol
(UDP) header.


### -field _HEADER_FIELD

 


### -field FieldValue



The value that the miniport adapter compares to the corresponding header field value in incoming packets. The location of the header field value is determined by the field type that is specified in the <b>HeaderField</b> member.

For more information, see the Remarks section.

This union contains the following members:



#### FieldByteValue

A <b>UCHAR</b> value to compare with a field in a network packet.

<div class="alert"><b>Note</b>  If the <b>MacHeaderField</b> member specifies an <b>NdisMacHeaderFieldPacketType</b> enumeration value, this member contains an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451556">NDIS_MAC_PACKET_TYPE</a> enumeration value.</div>
<div> </div>


#### FieldShortValue

A <b>USHORT</b> value to compare with a field in a network packet.



#### FieldLongValue

A <b>ULONG</b> value to compare with a field in a network packet.



#### FieldLong64Value

A <b>ULONG64</b> value to compare with a field in a network packet.



#### FieldByteArrayValue

A <b>UCHAR</b> array to compare with a field in a network packet.


### -field _FIELD_VALUE

 


### -field ResultValue

A union that contains a test result value. 

If the <b>ReceiveFilterTest</b> member is set to  <b>NdisReceiveFilterTestMaskEqual</b>, the network adapter first calculates a result from the value in the <b>FieldValue</b> member and the header field value as specified by the <b>HeaderField</b> member. The adapter then compares the calculated result with <b>ResultValue</b>. 

For more information, see the Remarks section.

This union contains the following members:



#### ResultByteValue

A <b>UCHAR</b> value to compare with a test result.



#### ResultShortValue

A <b>USHORT</b> value to compare with a test result.



#### ResultLongValue

A <b>ULONG</b> value to compare with a test result.



#### ResultLong64Value

A <b>ULONG64</b> value to compare with a test result.



#### ResultByteArrayValue

A <b>UCHAR</b> array to compare with a test result.


### -field _RESULT_VALUE

 




## -remarks



The <b>NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</b> structure specifies the filter test criterion for one field
    in a possible array of field tests that can be specified with the 
    <a href="https://msdn.microsoft.com/39dc6b3a-f24d-4f1a-96f8-416fbcb3f894">
    NDIS_RECEIVE_FILTER_PARAMETERS</a> structure.

The following table describes how the network adapter uses the <b>ReceiveFilterTest</b>, <b>FieldValue</b>, and <b>ResultValue</b> members to perform a filter test on the specified header field value of a received packet.

<table>
<tr>
<th><b>ReceiveFilterTest</b> value</th>
<th>Filter test performed by network adapter</th>
</tr>
<tr>
<td>NdisReceiveFilterTestEqual</td>
<td>(&lt;<i>header field value</i>&gt; == <b>FieldValue</b>)</td>
</tr>
<tr>
<td>NdisReceiveFilterTestMaskEqual</td>
<td>((&lt;<i>header field value</i>&gt; &amp; <b>FieldValue</b>) == <b>ResultValue</b>)</td>
</tr>
<tr>
<td>NdisReceiveFilterTestNotEqual</td>
<td>(&lt;<i>header field value</i>&gt; != <b>FieldValue</b>)</td>
</tr>
</table>
 

<div class="alert"><b>Note</b>  All the multibyte field and result values, such as the <b>FieldShortValue</b> and <b>ResultLong64Value</b> members, must be specified in network byte order (<i>big-endian</i>) format.</div>
<div> </div>
If the <b>NDIS_RECEIVE_FILTER_FIELD_MAC_HEADER_VLAN_UNTAGGED_OR_ZERO</b> flag is not set and there is no VLAN identifier filter that was configured by an OID set request of
       <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-set-filter">OID_RECEIVE_FILTER_SET_FILTER</a>, the miniport driver must do one of the following:

<ul>
<li>
For NDIS 6.20, the miniport driver must return a failed status for the
       OID request of <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-set-filter">OID_RECEIVE_FILTER_SET_FILTER</a>.

</li>
<li>
Starting with NDIS 6.30, if the <b>NDIS_RECEIVE_FILTER_FIELD_MAC_HEADER_VLAN_UNTAGGED_OR_ZERO</b> flag is not set and there is no VLAN identifier filter configured by the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-set-filter">OID_RECEIVE_FILTER_SET_FILTER</a> method request, the miniport driver must do either one of the following:

<ul>
<li>
The miniport driver must return a failed status for the
       <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-set-filter">OID_RECEIVE_FILTER_SET_FILTER</a> method request.

</li>
<li>
The miniport driver  must configure the network adapter  to inspect and filter the specified MAC address fields. If a VLAN tag is present in the received packet, the network adapter must remove it from the packet data. The miniport driver must   put the VLAN tag in an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566565">NDIS_NET_BUFFER_LIST_8021Q_INFO</a> that is associated with the packet's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.

</li>
</ul>
</li>
</ul>
Starting with NDIS 6.30, if the <b>NDIS_RECEIVE_FILTER_FIELD_MAC_HEADER_VLAN_UNTAGGED_OR_ZERO</b> flag is not set and there is a non-zero VLAN identifier filter that was configured by an OID set request of
       <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-set-filter">OID_RECEIVE_FILTER_SET_FILTER</a>, the miniport driver must do the following:

<ul>
<li>
The miniport driver must configure the network adapter  to inspect and filter the specified MAC address and VLAN identifier fields. 

If a VLAN tag is present in the received packet, the network adapter must remove it from the packet data. The miniport driver must   put the VLAN tag in an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566565">NDIS_NET_BUFFER_LIST_8021Q_INFO</a> that is associated with the packet's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451542">NDIS_ARP_HEADER_FIELD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565581">NDIS_FRAME_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451553">NDIS_IPV4_HEADER_FIELD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451554">NDIS_IPV6_HEADER_FIELD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565889">NDIS_MAC_HEADER_FIELD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451556">NDIS_MAC_PACKET_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/39dc6b3a-f24d-4f1a-96f8-416fbcb3f894">
   NDIS_RECEIVE_FILTER_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567183">NDIS_RECEIVE_FILTER_TEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439829">NDIS_UDP_HEADER_FIELD</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-set-filter">OID_RECEIVE_FILTER_SET_FILTER</a>
 

 

