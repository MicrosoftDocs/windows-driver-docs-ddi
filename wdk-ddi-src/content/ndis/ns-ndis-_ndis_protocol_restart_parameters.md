---
UID: NS:ndis._NDIS_PROTOCOL_RESTART_PARAMETERS
title: _NDIS_PROTOCOL_RESTART_PARAMETERS (ndis.h)
description: The NDIS_PROTOCOL_RESTART_PARAMETERS structure defines restart parameters for a protocol driver when NDIS calls the ProtocolNetPnPEvent function to indicate a NetEventRestart event.
old-location: netvista\ndis_protocol_restart_parameters.htm
tech.root: netvista
ms.assetid: 722287da-e0ee-41d5-b85a-0ec55eac41b9
ms.date: 05/02/2018
keywords: ["_NDIS_PROTOCOL_RESTART_PARAMETERS structure"]
ms.keywords: "*PNDIS_PROTOCOL_RESTART_PARAMETERS, NDIS_PROTOCOL_RESTART_PARAMETERS, NDIS_PROTOCOL_RESTART_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_PROTOCOL_RESTART_PARAMETERS, PNDIS_PROTOCOL_RESTART_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PROTOCOL_RESTART_PARAMETERS, ndis/NDIS_PROTOCOL_RESTART_PARAMETERS, ndis/PNDIS_PROTOCOL_RESTART_PARAMETERS, netvista.ndis_protocol_restart_parameters, protocol_structures_ref_1a426da7-b2f9-49b0-9069-24ceddcd8ad1.xml"
f1_keywords:
 - "ndis/NDIS_PROTOCOL_RESTART_PARAMETERS"
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
- NDIS_PROTOCOL_RESTART_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_PROTOCOL_RESTART_PARAMETERS, *PNDIS_PROTOCOL_RESTART_PARAMETERS
---

# _NDIS_PROTOCOL_RESTART_PARAMETERS structure


## -description


The NDIS_PROTOCOL_RESTART_PARAMETERS structure defines restart parameters for a protocol driver when
  NDIS calls the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a> function to
  indicate a 
  <b>NetEventRestart</b> event.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_PROTOCOL_RESTART_PARAMETERS structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_PROTOCOL_RESTART_PARAMETERS, the 
     <b>Revision</b> member to NDIS_PROTOCOL_RESTART_PARAMETERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_PROTOCOL_RESTART_PARAMETERS_REVISION_1.


### -field FilterModuleNameBuffer

A list of the names of the underlying filter modules. For each name, the buffer contains a USHORT
     value followed by a wide character string. Use the first USHORT value in the buffer to determine the
     length of the first string. Use the length of the first string to determine the start of the next
     string. Continue in this manner until the number of bytes that are retrieved from the buffer equals the
     number of bytes that are specified in the 
     <b>FilterModuleNameBufferLength</b> member.


### -field FilterModuleNameBufferLength

The length, in bytes, of the buffer in the 
     <b>FilterModuleNameBuffer</b> member.


### -field RestartAttributes

A pointer to the first entry in a list of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_restart_attributes">NDIS_RESTART_ATTRIBUTES</a> structures.
     Use the 
     <b>Next</b> member of the NDIS_RESTART_ATTRIBUTES structure to get the next structure in the list.


### -field BoundIfIndex

The NDIS network interface index of the highest-level interface that is stacked on the miniport
     adapter. That is, if there are virtual miniports or filter modules that are installed over the miniport
     adapter, this member is the 
     <i>IfIndex</i> of the highest-level virtual miniport or filter module.


### -field BoundIfNetluid

The NDIS 
     <a href="https://docs.microsoft.com/windows/win32/api/ifdef/ns-ifdef-net_luid_lh">NET_LUID</a> value (that is also the network interface
     name (<i>ifName</i> in 
     RFC 2863)) of the highest-level interface that is stacked on the miniport
     adapter. That is, if there are virtual miniports or filter modules that are installed over the miniport
     adapter, this member is the NET_LUID value of the highest-level virtual miniport or filter
     module.


### -field Flags

Reserved for future use.


## -remarks



NDIS passes an NDIS_PROTOCOL_RESTART_PARAMETERS structure to a protocol driver when it calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a> function to
    indicate a 
    <b>NetEventRestart</b> event.

Each name that is specified in the buffer in the 
    <b>FilterModuleNameBuffer</b> member is not guaranteed to be NULL-terminated. The USHORT value at the
    start of each string contains the length, in bytes, of the string. Protocol drivers should check the
    value of the 
    <b>FilterModuleNameBufferLength</b> member before they access the buffer.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_restart_attributes">NDIS_RESTART_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a>
 

 

