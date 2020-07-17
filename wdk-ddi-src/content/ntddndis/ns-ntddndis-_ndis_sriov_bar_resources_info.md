---
UID: NS:ntddndis._NDIS_SRIOV_BAR_RESOURCES_INFO
title: _NDIS_SRIOV_BAR_RESOURCES_INFO (ntddndis.h)
description: The NDIS_SRIOV_BAR_RESOURCES_INFO structure specifies the PCI Express (PCIe) Base Address Register (BAR) of a network adapter's PCIe Virtual Function (VF).
old-location: netvista\ndis_sriov_bar_resources_info.htm
tech.root: netvista
ms.assetid: e5a5ac98-171d-4a31-8bc6-400f613b7dc9
ms.date: 05/02/2018
keywords: ["_NDIS_SRIOV_BAR_RESOURCES_INFO structure"]
ms.keywords: "*PNDIS_SRIOV_BAR_RESOURCES_INFO, NDIS_SRIOV_BAR_RESOURCES_INFO, NDIS_SRIOV_BAR_RESOURCES_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_SRIOV_BAR_RESOURCES_INFO, PNDIS_SRIOV_BAR_RESOURCES_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SRIOV_BAR_RESOURCES_INFO, netvista.ndis_sriov_bar_resources_info, ntddndis/NDIS_SRIOV_BAR_RESOURCES_INFO, ntddndis/PNDIS_SRIOV_BAR_RESOURCES_INFO"
f1_keywords:
 - "ntddndis/NDIS_SRIOV_BAR_RESOURCES_INFO"
 - "NDIS_SRIOV_BAR_RESOURCES_INFO"
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
- NDIS_SRIOV_BAR_RESOURCES_INFO
product:
- Windows
targetos: Windows
req.typenames: NDIS_SRIOV_BAR_RESOURCES_INFO, *PNDIS_SRIOV_BAR_RESOURCES_INFO
---

# _NDIS_SRIOV_BAR_RESOURCES_INFO structure


## -description


The <b>NDIS_SRIOV_BAR_RESOURCES_INFO</b> structure specifies the PCI Express (PCIe) Base Address Register (BAR) of a network adapter's PCIe Virtual Function (VF). 


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SRIOV_BAR_RESOURCES_INFO</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SRIOV_BAR_RESOURCES_INFO</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_SRIOV_BAR_RESOURCES_INFO_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_SRIOV_BAR_RESOURCES_INFO_REVISION_1.


### -field VFId

An NDIS_SRIOV_FUNCTION_ID value that specifies the unique identifier of the VF on the network adapter.

<div class="alert"><b>Note</b>  The VF with the specified NDIS_SRIOV_FUNCTION_ID value must have resources that were previously allocated through an OID set request of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-nic-switch-allocate-vf">OID_NIC_SWITCH_ALLOCATE_VF</a>.

</div>
<div> </div>

### -field BarIndex

A USHORT value that specifies the BAR index on the VF. This value is the offset of the register within the table of BARs in the PCI configuration space.


### -field BarResourcesOffset

A ULONG value that specifies the offset, in units of bytes, from the beginning of this structure to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure.


## -remarks



The <b>NDIS_SRIOV_BAR_RESOURCES_INFO</b> structure is used in OID method requests of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-sriov-bar-resources">OID_SRIOV_BAR_RESOURCES</a>.  




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-sriov-bar-resources">OID_SRIOV_BAR_RESOURCES</a>
 

 

