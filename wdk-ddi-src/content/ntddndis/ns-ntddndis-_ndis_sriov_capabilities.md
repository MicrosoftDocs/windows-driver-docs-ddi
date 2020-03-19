---
UID: NS:ntddndis._NDIS_SRIOV_CAPABILITIES
title: _NDIS_SRIOV_CAPABILITIES (ntddndis.h)
description: The NDIS_SRIOV_CAPABILITIES structure specifies the single root I/O virtualization (SR-IOV) capabilities of the network adapter.
old-location: netvista\ndis_sriov_capabilities.htm
tech.root: netvista
ms.assetid: 57cf980c-4477-4c12-8d82-7a8df8b2922f
ms.date: 05/02/2018
keywords: ["_NDIS_SRIOV_CAPABILITIES structure"]
ms.keywords: "*PNDIS_SRIOV_CAPABILITIES, NDIS_SRIOV_CAPABILITIES, NDIS_SRIOV_CAPABILITIES structure [Network Drivers Starting with Windows Vista], PNDIS_SRIOV_CAPABILITIES, PNDIS_SRIOV_CAPABILITIES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SRIOV_CAPABILITIES, netvista.ndis_sriov_capabilities, ntddndis/NDIS_SRIOV_CAPABILITIES, ntddndis/PNDIS_SRIOV_CAPABILITIES"
f1_keywords:
 - "ntddndis/NDIS_SRIOV_CAPABILITIES"
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
- NDIS_SRIOV_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: NDIS_SRIOV_CAPABILITIES, *PNDIS_SRIOV_CAPABILITIES
---

# _NDIS_SRIOV_CAPABILITIES structure


## -description


The <b>NDIS_SRIOV_CAPABILITIES</b> structure specifies the single root I/O virtualization (SR-IOV) capabilities of the network adapter.


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SRIOV_CAPABILITIES</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SRIOV_CAPABILITIES</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_SRIOV_CAPABILITIES _REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_SRIOV_CAPABILITIES _REVISION_1.


### -field Flags

A ULONG value that contains a bitwise OR of flags. This member is reserved for NDIS


### -field SriovCapabilities

A ULONG value that contains a bitwise OR of the following flags:





#### NDIS_SRIOV_CAPS_SRIOV_SUPPORTED

Specifies that the network adapter supports SR-IOV functionality. 

<div class="alert"><b>Note</b>  This flag must only be set by the miniport driver for the PCI Express (PCIe) Physical Function (PF) of the network adapter. This driver runs in the management operating system. This operating system runs in the Hyper-V parent partition.</div>
<div> </div>


#### NDIS_SRIOV_CAPS_PF_MINIPORT

Specifies that this is a PF  miniport driver. 



#### NDIS_SRIOV_CAPS_VF_MINIPORT

Specifies that this is a PCIe  Virtual Function (VF) miniport driver. 


## -remarks



 The miniport driver uses the <b>NDIS_SRIOV_CAPABILITIES</b> structure to report its SR-IOV capabilities in the following ways:

<ul>
<li>
The  miniport driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a> function from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function and sets the <i>MiniportAttributes</i> parameter to a pointer to an  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes">NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a> structure. The driver advertises SR-IOV support by formatting the 
<b>HardwareSriovCapabilities</b> and <b>CurrentSriovCapabilities</b> members as <b>NDIS_SRIOV_CAPABILITIES</b> structures.

</li>
<li>When the driver successfully handles an OID query request of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-sriov-hardware-capabilities">OID_SRIOV_HARDWARE_CAPABILITIES</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-sriov-current-capabilities">OID_SRIOV_CURRENT_CAPABILITIES</a>, it returns an <b>NDIS_SRIOV_CAPABILITIES</b> structure.</li>
</ul>
NDIS passes the network adapter's SR-IOV capabilities to overlying drivers that bind to the network adapter in the following way:

<ul>
<li>
When NDIS calls an overlying filter driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function, NDIS passes the network adapter's SR-IOV capabilities through the <i>AttachParameters</i> parameter.  This parameter contains a pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_filter_attach_parameters">NDIS_FILTER_ATTACH_PARAMETERS</a> structure. The <b>SriovCapabilities</b>  member of this structure contains a pointer to an <b>NDIS_SRIOV_CAPABILITIES</b> structure.

</li>
<li>
When NDIS calls an overlying protocol driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>
 function, NDIS passes the network adapter's SR-IOV capabilities through the <i>BindParameters</i> parameter.  This parameter contains a pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_filter_attach_parameters">NDIS_FILTER_ATTACH_PARAMETERS</a> structure. The <b>SriovCapabilities</b>  member of this structure contains a pointer to an <b>NDIS_SRIOV_CAPABILITIES</b> structure.

</li>
</ul>
For more information on how to report the SR-IOV capabilities of a network adapter, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/determining-sr-iov-capabilities">Determining SR-IOV Capabilities</a>.




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_filter_attach_parameters">NDIS_FILTER_ATTACH_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes">NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-sriov-current-capabilities">OID_SRIOV_CURRENT_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-sriov-hardware-capabilities">OID_SRIOV_HARDWARE_CAPABILITIES</a>
 

 

