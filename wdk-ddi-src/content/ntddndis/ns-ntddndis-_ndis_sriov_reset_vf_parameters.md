---
UID: NS:ntddndis._NDIS_SRIOV_RESET_VF_PARAMETERS
title: "_NDIS_SRIOV_RESET_VF_PARAMETERS"
description: The NDIS_SRIOV_RESET_VF_PARAMETERS structure specifies the parameters for resetting a network adapter's PCI Express (PCIe) Virtual Function (VF).
old-location: netvista\ndis_sriov_reset_vf_parameters.htm
tech.root: netvista
ms.assetid: 0f3c1da5-7e1d-4e13-9942-bedb9ddaf541
ms.date: 05/02/2018
ms.keywords: "*PNDIS_SRIOV_RESET_VF_PARAMETERS, NDIS_SRIOV_RESET_VF_PARAMETERS, NDIS_SRIOV_RESET_VF_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_SRIOV_RESET_VF_PARAMETERS, PNDIS_SRIOV_RESET_VF_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SRIOV_RESET_VF_PARAMETERS, netvista.ndis_sriov_reset_vf_parameters, ntddndis/NDIS_SRIOV_RESET_VF_PARAMETERS, ntddndis/PNDIS_SRIOV_RESET_VF_PARAMETERS"
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_SRIOV_RESET_VF_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_SRIOV_RESET_VF_PARAMETERS, *PNDIS_SRIOV_RESET_VF_PARAMETERS
---

# _NDIS_SRIOV_RESET_VF_PARAMETERS structure


## -description


The <b>NDIS_SRIOV_RESET_VF_PARAMETERS</b> structure specifies the parameters for resetting a network adapter's PCI Express (PCIe) Virtual Function (VF).


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SRIOV_RESET_VF_PARAMETERS</b> structure. This member is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SRIOV_RESET_VF_PARAMETERS</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_SRIOV_RESET_VF_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_SRIOV_RESET_VF_PARAMETERS_REVISION_1.


### -field VFId

An NDIS_SRIOV_FUNCTION_ID value that specifies the unique identifier of the VF on the network adapter.

<div class="alert"><b>Note</b>  The VF with the specified NDIS_SRIOV_FUNCTION_ID value must have resources that were previously allocated through an OID set request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>.

</div>
<div> </div>

## -remarks



The <b>NDIS_SRIOV_RESET_VF_PARAMETERS</b> structure is used in OID set requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451889">OID_SRIOV_RESET_VF</a>. 




## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451889">OID_SRIOV_RESET_VF</a>
 

 

