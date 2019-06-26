---
UID: NS:ntddndis._NDIS_NIC_SWITCH_DELETE_VPORT_PARAMETERS
title: _NDIS_NIC_SWITCH_DELETE_VPORT_PARAMETERS (ntddndis.h)
description: The NDIS_NIC_SWITCH_DELETE_VPORT_PARAMETERS structure specifies the information about a virtual port (VPort) that will be deleted from a network adapter switch on the network adapter.
old-location: netvista\ndis_nic_switch_delete_vport_parameters.htm
tech.root: netvista
ms.assetid: 7cbdaa08-51c9-495d-a5c7-bb2c4009d7a4
ms.date: 05/02/2018
ms.keywords: "*PNDIS_NIC_SWITCH_DELETE_VPORT_PARAMETERS, NDIS_NIC_SWITCH_DELETE_VPORT_PARAMETERS, NDIS_NIC_SWITCH_DELETE_VPORT_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_NIC_SWITCH_DELETE_VPORT_PARAMETERS, PNDIS_NIC_SWITCH_DELETE_VPORT_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NIC_SWITCH_DELETE_VPORT_PARAMETERS, netvista.ndis_nic_switch_delete_vport_parameters, ntddndis/NDIS_NIC_SWITCH_DELETE_VPORT_PARAMETERS, ntddndis/PNDIS_NIC_SWITCH_DELETE_VPORT_PARAMETERS"
ms.topic: struct
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
- NDIS_NIC_SWITCH_DELETE_VPORT_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_NIC_SWITCH_DELETE_VPORT_PARAMETERS, *PNDIS_NIC_SWITCH_DELETE_VPORT_PARAMETERS
---

# _NDIS_NIC_SWITCH_DELETE_VPORT_PARAMETERS structure


## -description


The <b>NDIS_NIC_SWITCH_DELETE_VPORT_PARAMETERS</b> structure specifies the information about a virtual port (VPort) that will be deleted from a network adapter switch on the network adapter. 


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_NIC_SWITCH_DELETE_VPORT_PARAMETERS</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_NIC_SWITCH_DELETE_VPORT_PARAMETERS</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_NIC_SWITCH_DELETE_VPORT_PARAMETERS_REVISION_1

Original version for NDIS 6.30.

Set the <b>Size</b> member to NDIS_SIZEOF_NIC_SWITCH_DELETE_VPORT_PARAMETERS_REVISION_1.


### -field Flags

A ULONG value that contains a bitwise OR of flags. This member is reserved for NDIS.


### -field VPortId

An NDIS_NIC_SWITCH_VPORT_ID value  that uniquely identifies the virtual port (VPort) to be deleted. The VPort with the specified NDIS_NIC_SWITCH_VPORT_ID value must have previously been created through an OID set request of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-nic-switch-create-vport">OID_NIC_SWITCH_CREATE_VPORT</a>.

<div class="alert"><b>Note</b>  The default VPort that is attached to the PCI Express (PCIe) Physical Function (PF) cannot be deleted. The <b>VPortId</b> member must not be set to  DEFAULT_PORT_NUMBER.</div>
<div> </div>

## -remarks



The NDIS_NIC_SWITCH_DELETE_PORT_PARAMETERS structure is used in OID set requests of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-nic-switch-delete-vport">OID_NIC_SWITCH_DELETE_VPORT</a>. 




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-nic-switch-create-vport">OID_NIC_SWITCH_CREATE_VPORT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-nic-switch-delete-vport">OID_NIC_SWITCH_DELETE_VPORT</a>
 

 

