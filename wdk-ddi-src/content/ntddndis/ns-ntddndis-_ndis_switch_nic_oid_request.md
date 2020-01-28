---
UID: NS:ntddndis._NDIS_SWITCH_NIC_OID_REQUEST
title: _NDIS_SWITCH_NIC_OID_REQUEST (ntddndis.h)
description: The NDIS_SWITCH_NIC_OID_REQUEST structure specifies the information that is required to forward or originate OID requests.
old-location: netvista\ndis_switch_nic_oid_request.htm
tech.root: netvista
ms.assetid: 0a097769-0c74-4465-b339-13696b4dbb6b
ms.date: 05/02/2018
ms.keywords: "*PNDIS_SWITCH_NIC_OID_REQUEST, NDIS_SWITCH_NIC_OID_REQUEST, NDIS_SWITCH_NIC_OID_REQUEST structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_NIC_OID_REQUEST, PNDIS_SWITCH_NIC_OID_REQUEST structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_NIC_OID_REQUEST, netvista.ndis_switch_nic_oid_request, ntddndis/NDIS_SWITCH_NIC_OID_REQUEST, ntddndis/PNDIS_SWITCH_NIC_OID_REQUEST"
f1_keywords:
 - "ntddndis/NDIS_SWITCH_NIC_OID_REQUEST"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddndis.h
api_name:
- NDIS_SWITCH_NIC_OID_REQUEST
product:
- Windows
targetos: Windows
req.typenames: NDIS_SWITCH_NIC_OID_REQUEST, *PNDIS_SWITCH_NIC_OID_REQUEST
---

# _NDIS_SWITCH_NIC_OID_REQUEST structure


## -description


The <b>NDIS_SWITCH_NIC_OID_REQUEST</b> structure specifies the information that is required to forward or originate OID requests.


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_NIC_OID_REQUEST</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_NIC_OID_REQUEST</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 





#### NDIS_SWITCH_NIC_OID_REQUEST_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_NIC_OID_REQUEST_REVISION_1.


### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.




### -field SourcePortId

An NDIS_SWITCH_PORT_ID value that contains the unique identifier of the Hyper-V extensible switch port to which the OID request was originally issued.




### -field SourceNicIndex

An NDIS_SWITCH_NIC_INDEX value that specifies the index of the source network adapter that is connected to the source extensible switch port specified by the <b>SourcePortId</b> member.


### -field DestinationPortId

An NDIS_SWITCH_PORT_ID value that contains the unique identifier of the extensible switch port to which the OID request is to be forwarded.




### -field DestinationNicIndex

An NDIS_SWITCH_NIC_INDEX value that specifies the index of the destination network adapter that is connected to the  extensible switch port specified by the <b>DestinationPortId</b> member.


### -field OidRequest

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure. This structure contains the data for the OID request that will be forwarded to the miniport driver of the network adapter specified by the <b>DestinationPortId</b> and <b>DestinationNicIndex</b> members.


## -remarks



The <b>NDIS_SWITCH_NIC_OID_REQUEST</b> structure is used in OID method requests of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-request">OID_SWITCH_NIC_REQUEST</a>.

A extension can forward or originate OID requests to underlying physical network adapters in the extensible switch driver stack. This enables an extension to do the following:

<ul>
<li>
Manage the configuration of hardware offloads on an underlying physical adapter for the following offload technologies:

<ul>
<li>
Internet Protocol security (IPsec).

</li>
<li>
Virtualized machine queue (VMQ).

</li>
<li>
Single root I/O virtualization (SR-IOV).

</li>
</ul>
</li>
<li>
Query the configuration of an underlying physical network adapter by issuing standard NDIS OIDs. For example, the extension can issue an OID query request of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-802-3-current-address">OID_802_3_CURRENT_ADDRESS</a> to obtain the adapter's current media access control (MAC) address.

</li>
</ul>
For guidelines on how to issue OID requests to underlying physical adapters, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/managing-oid-requests-to-physical-network-adapters">Managing OID Requests to Physical Network Adapters</a>.




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-request">OID_SWITCH_NIC_REQUEST</a>
 

 

