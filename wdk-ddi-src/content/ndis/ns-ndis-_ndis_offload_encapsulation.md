---
UID: NS:ndis._NDIS_OFFLOAD_ENCAPSULATION
title: _NDIS_OFFLOAD_ENCAPSULATION (ndis.h)
description: The NDIS_OFFLOAD_ENCAPSULATION structure specifies encapsulation settings when it is used with the OID_OFFLOAD_ENCAPSULATION OID.
old-location: netvista\ndis_offload_encapsulation.htm
tech.root: netvista
ms.assetid: 19013ffa-6bb5-4a77-b85b-c32fb0bf0530
ms.date: 05/02/2018
ms.keywords: "*PNDIS_OFFLOAD_ENCAPSULATION, NDIS_ENCAPSULATION_IEEE_802_3, NDIS_ENCAPSULATION_IEEE_LLC_SNAP_ROUTED, NDIS_OFFLOAD_ENCAPSULATION, NDIS_OFFLOAD_ENCAPSULATION structure [Network Drivers Starting with Windows Vista], PNDIS_OFFLOAD_ENCAPSULATION, PNDIS_OFFLOAD_ENCAPSULATION structure pointer [Network Drivers Starting with Windows Vista], _NDIS_OFFLOAD_ENCAPSULATION, ndis/NDIS_OFFLOAD_ENCAPSULATION, ndis/PNDIS_OFFLOAD_ENCAPSULATION, netvista.ndis_offload_encapsulation, tcpip_offload_ref_d3154816-5813-4616-b17f-b76362d9a58f.xml"
f1_keywords:
 - "ndis/NDIS_OFFLOAD_ENCAPSULATION"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NDIS_OFFLOAD_ENCAPSULATION
product:
- Windows
targetos: Windows
req.typenames: NDIS_OFFLOAD_ENCAPSULATION, *PNDIS_OFFLOAD_ENCAPSULATION
---

# _NDIS_OFFLOAD_ENCAPSULATION structure


## -description


The NDIS_OFFLOAD_ENCAPSULATION structure specifies encapsulation settings when it is used with the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-offload-encapsulation">OID_OFFLOAD_ENCAPSULATION</a> OID.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_OFFLOAD_ENCAPSULATION structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_OFFLOAD_ENCAPSULATION, the 
     <b>Revision</b> member to NDIS_OFFLOAD_ENCAPSULATION_ REVISION _1, and the 
     <b>Size</b> member to NDIS_SIZEOF_OFFLOAD_ENCAPSULATION_REVISION_1.


### -field IPv4

A structure within NDIS_OFFLOAD_ENCAPSULATION that specifies IPv4 encapsulation and that contains
     the following members:
     


### -field IPv4.Enabled

A ULONG value that enables IPv4 encapsulation. A protocol driver sets 
       <b>Enabled</b> to NDIS_OFFLOAD_SET_ON if it is enabling IPv4 large send offload version 1 (LSOV1),
       large send offload version 2 (LSOV2), or checksum offloads. If a protocol driver is deactivating all offloads, it sets <b>Enabled</b> to NDIS_OFFLOAD_SET_OFF. Otherwise, the protocol driver sets 
       <b>Enabled</b> to NDIS_OFFLOAD_SET_NO_CHANGE.


### -field IPv4.EncapsulationType

The IPv4 encapsulation type. If the 
       <b>Enabled</b> member is not set to NDIS_OFFLOAD_SET_ON, this member is zero. If the 
       <b>Enabled</b> member is set to NDIS_OFFLOAD_SET_ON, a protocol driver must set 
       <b>EncapsulationType</b> to one of the following:
       

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDIS_ENCAPSULATION_IEEE_802_3"></a><a id="ndis_encapsulation_ieee_802_3"></a><dl>
<dt><b>NDIS_ENCAPSULATION_IEEE_802_3</b></dt>
</dl>
</td>
<td width="60%">
Specifies IEEE 802.3 encapsulation. When this value is specified, a miniport driver should also use NDIS_ENCAPSULATION_IEEE_802_3_P_AND_Q or NDIS_ENCAPSULATION_IEEE_802_3_P_AND_Q_IN_OOB encapsulation where applicable. See documentation for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_offload">NDIS_OFFLOAD</a> for more information.


</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_ENCAPSULATION_IEEE_LLC_SNAP_ROUTED"></a><a id="ndis_encapsulation_ieee_llc_snap_routed"></a><dl>
<dt><b>NDIS_ENCAPSULATION_IEEE_LLC_SNAP_ROUTED</b></dt>
</dl>
</td>
<td width="60%">
Specifies logical link control (LLC) encapsulation for routed protocols, as described in RFC
         1483. This flag is also used to indicate Ethernet LLC/SNAP encapsulation.

</td>
</tr>
</table>
 


### -field IPv4.HeaderSize

The Ethernet header length that is used in IPv4 packets. If the 
       <b>Enabled</b> member is not set to NDIS_OFFLOAD_SET_ON, this member is zero. If the 
       <b>Enabled</b> member is set to NDIS_OFFLOAD_SET_ON, a protocol driver must set 
       <b>HeaderSize</b> to the size of the Ethernet header that it uses.


### -field IPv6

A structure within NDIS_OFFLOAD_ENCAPSULATION that specifies IPv6 encapsulation and that contains
     the following members:
     


### -field IPv6.Enabled

A ULONG value that enables IPv6 encapsulation. A protocol driver sets 
       <b>Enabled</b> to NDIS_OFFLOAD_SET_ON if it is enabling IPv6 LSOV1, LSOV2, or checksum offloads.
       If a protocol driver is deactivating all offloads, it sets <b>Enabled</b> to NDIS_OFFLOAD_SET_OFF. Otherwise, the protocol driver sets 
       <b>Enabled</b> to NDIS_OFFLOAD_SET_NO_CHANGE.


### -field IPv6.EncapsulationType

The IPv6 encapsulation type. If the 
       <b>Enabled</b> member is not set to NDIS_OFFLOAD_SET_ON, 
       <b>EncapsulationType</b> is zero. If the 
       <b>Enabled</b> member is set to NDIS_OFFLOAD_SET_ON, a protocol driver must set 
       <b>EncapsulationType</b> to one of the following:
       

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDIS_ENCAPSULATION_IEEE_802_3"></a><a id="ndis_encapsulation_ieee_802_3"></a><dl>
<dt><b>NDIS_ENCAPSULATION_IEEE_802_3</b></dt>
</dl>
</td>
<td width="60%">
Specifies IEEE 802.3 encapsulation. When this value is specified, a miniport driver should also use NDIS_ENCAPSULATION_IEEE_802_3_P_AND_Q or NDIS_ENCAPSULATION_IEEE_802_3_P_AND_Q_IN_OOB encapsulation where applicable. See documentation for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_offload">NDIS_OFFLOAD</a> for more information.


</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_ENCAPSULATION_IEEE_LLC_SNAP_ROUTED"></a><a id="ndis_encapsulation_ieee_llc_snap_routed"></a><dl>
<dt><b>NDIS_ENCAPSULATION_IEEE_LLC_SNAP_ROUTED</b></dt>
</dl>
</td>
<td width="60%">
Specifies LLC encapsulation for routed protocols, as described in RFC 1483. This flag is also
         used to indicate Ethernet LLC/SNAP encapsulation.

</td>
</tr>
</table>
 


### -field IPv6.HeaderSize

The Ethernet header length that is used in IPv6 packets. If the 
       <b>Enabled</b> member is not set to NDIS_OFFLOAD_SET_ON, this member is zero. If the 
       <b>Enabled</b> member is set to NDIS_OFFLOAD_SET_ON, a protocol driver must set 
       <b>HeaderSize</b> to the size of the Ethernet header that it uses.


## -remarks



The NDIS_OFFLOAD_ENCAPSULATION structure specifies the requested encapsulation settings that a
    miniport adapter should use for task offload services.

In a set of 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-offload-encapsulation">OID_OFFLOAD_ENCAPSULATION</a>, a
    protocol driver specifies an NDIS_OFFLOAD_ENCAPSULATION structure in the 
    <b>InformationBuffer</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-offload-encapsulation">OID_OFFLOAD_ENCAPSULATION</a>
 

 

