---
UID: NS:encapsulationconfig._NDIS_OFFLOAD_ENCAPSULATION
title: NDIS_OFFLOAD_ENCAPSULATION
ms.date: 11/30/2020
targetos: Windows
description: The NDIS_OFFLOAD_ENCAPSULATION structure specifies encapsulation settings when it is used with the OID_OFFLOAD_ENCAPSULATION OID.
tech.root: netvista
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ndis/encapsulationconfig.h
req.include-header: ndis.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: NDIS_OFFLOAD_ENCAPSULATION, *PNDIS_OFFLOAD_ENCAPSULATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - encapsulationconfig.h
api_name:
 - _NDIS_OFFLOAD_ENCAPSULATION
 - PNDIS_OFFLOAD_ENCAPSULATION
 - NDIS_OFFLOAD_ENCAPSULATION
f1_keywords:
 - _NDIS_OFFLOAD_ENCAPSULATION
 - encapsulationconfig/_NDIS_OFFLOAD_ENCAPSULATION
 - PNDIS_OFFLOAD_ENCAPSULATION
 - encapsulationconfig/PNDIS_OFFLOAD_ENCAPSULATION
 - NDIS_OFFLOAD_ENCAPSULATION
 - encapsulationconfig/NDIS_OFFLOAD_ENCAPSULATION
dev_langs:
 - c++
---

# _NDIS_OFFLOAD_ENCAPSULATION structure


## -description

The NDIS_OFFLOAD_ENCAPSULATION structure specifies encapsulation settings when it is used with the 
  <a href="/windows-hardware/drivers/network/oid-offload-encapsulation">OID_OFFLOAD_ENCAPSULATION</a> OID.

## -struct-fields

### -field Header

The 
     <a href="/windows-hardware/drivers/ddi/objectheader/ns-objectheader-ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
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
Specifies IEEE 802.3 encapsulation. When this value is specified, a miniport driver should also use NDIS_ENCAPSULATION_IEEE_802_3_P_AND_Q or NDIS_ENCAPSULATION_IEEE_802_3_P_AND_Q_IN_OOB encapsulation where applicable. See documentation for <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_offload">NDIS_OFFLOAD</a> for more information.


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
Specifies IEEE 802.3 encapsulation. When this value is specified, a miniport driver should also use NDIS_ENCAPSULATION_IEEE_802_3_P_AND_Q or NDIS_ENCAPSULATION_IEEE_802_3_P_AND_Q_IN_OOB encapsulation where applicable. See documentation for <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_offload">NDIS_OFFLOAD</a> for more information.


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
    <a href="/windows-hardware/drivers/network/oid-offload-encapsulation">OID_OFFLOAD_ENCAPSULATION</a>, a
    protocol driver specifies an NDIS_OFFLOAD_ENCAPSULATION structure in the 
    <b>InformationBuffer</b> member of the 
    <a href="/windows-hardware/drivers/ddi/oidrequest/ns-oidrequest-ndis_oid_request">NDIS_OID_REQUEST</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/objectheader/ns-objectheader-ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/oidrequest/ns-oidrequest-ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="/windows-hardware/drivers/network/oid-offload-encapsulation">OID_OFFLOAD_ENCAPSULATION</a>
