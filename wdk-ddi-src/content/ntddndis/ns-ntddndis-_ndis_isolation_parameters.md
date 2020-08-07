---
UID: NS:ntddndis._NDIS_ISOLATION_PARAMETERS
title: _NDIS_ISOLATION_PARAMETERS (ntddndis.h)
description: The NDIS_ISOLATION_PARAMETERS structure is used by the OID_GEN_ISOLATION_PARAMETERS OID to return the isolation parameters that are set on a VM network adapter's port.
old-location: netvista\ndis_isolation_parameters.htm
tech.root: netvista
ms.assetid: 71A01647-3415-4F76-A67C-D1022C8A11D9
ms.date: 05/02/2018
keywords: ["NDIS_ISOLATION_PARAMETERS structure"]
ms.keywords: "*PNDIS_ISOLATION_PARAMETERS, NDIS_ISOLATION_PARAMETERS, NDIS_ISOLATION_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_ISOLATION_PARAMETERS, PNDIS_ISOLATION_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_ISOLATION_PARAMETERS, netvista.ndis_isolation_parameters, ntddndis/NDIS_ISOLATION_PARAMETERS, ntddndis/PNDIS_ISOLATION_PARAMETERS"
f1_keywords:
 - "ntddndis/NDIS_ISOLATION_PARAMETERS"
 - "NDIS_ISOLATION_PARAMETERS"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.40 and later.
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
- NDIS_ISOLATION_PARAMETERS
targetos: Windows
req.typenames: NDIS_ISOLATION_PARAMETERS, *PNDIS_ISOLATION_PARAMETERS
---

# _NDIS_ISOLATION_PARAMETERS structure


## -description


The <b>NDIS_ISOLATION_PARAMETERS</b> structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-isolation-parameters">OID_GEN_ISOLATION_PARAMETERS</a> OID to return the isolation parameters that are set on a VM network adapter's port.


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_ISOLATION_PARAMETERS</b>  structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to <b>NDIS_OBJECT_TYPE_DEFAULT</b>. To specify the version of the <b>NDIS_ISOLATION_PARAMETERS</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 





#### NDIS_ISOLATION_PARAMETERS_REVISION_1

Original version for NDIS 6.40 and later.

Set the <b>Size</b> member to <b>NDIS_SIZEOF_NDIS_ISOLATION_PARAMETERS_REVISION_1</b>.


### -field Flags

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.




### -field IsolationMode

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_isolation_mode">NDIS_ISOLATION_MODE</a> enumeration value that specifies the isolation mode.


### -field AllowUntaggedTraffic

Specifies whether the VM network adapter's port is allowed to send or receive untagged packets. If untagged packets are allowed, the VM network adapter miniport driver tags untagged packets with the default isolation ID. Otherwise, the miniport driver drops them.


### -field NumRoutingDomainEntries

A <b>ULONG</b> value that specifies the number of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_routing_domain_entry">NDIS_ROUTING_DOMAIN_ENTRY</a> in the array that follows the <b>NDIS_ISOLATION_PARAMETERS</b> structure.


### -field FirstRoutingDomainEntryOffset

A <b>ULONG</b> value that specifies the offset, in bytes, to the first <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_routing_domain_entry">NDIS_ROUTING_DOMAIN_ENTRY</a> element in the array that follows the <b>NDIS_ISOLATION_PARAMETERS</b> structure. The offset is measured from the start of the <b>NDIS_ISOLATION_PARAMETERS</b> structure to the beginning of the first element of the array.

<div class="alert"><b>Note</b>  If the value of <b>NumRoutingDomainEntries</b> is zero, this member is ignored.</div>
<div> </div>

## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_isolation_mode">NDIS_ISOLATION_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-isolation-parameters-get-first-routing-domain-entry">NDIS_ISOLATION_PARAMETERS_GET_FIRST_ROUTING_DOMAIN_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_routing_domain_entry">NDIS_ROUTING_DOMAIN_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_isolation">NDIS_SWITCH_PORT_PROPERTY_ISOLATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-isolation-parameters">OID_GEN_ISOLATION_PARAMETERS</a>
 

 

