---
UID: NS:ntddndis._NDIS_NIC_SWITCH_FREE_VF_PARAMETERS
title: _NDIS_NIC_SWITCH_FREE_VF_PARAMETERS (ntddndis.h)
description: The NDIS_NIC_SWITCH_FREE_VF_PARAMETERS specifies a PCI Express (PCIe) Virtual Function (VF) whose resources will be freed.
old-location: netvista\ndis_nic_switch_free_vf_parameters.htm
tech.root: netvista
ms.assetid: 61f3839a-f428-4585-a046-edce85d829dd
ms.date: 05/02/2018
ms.keywords: "*PNDIS_NIC_SWITCH_FREE_VF_PARAMETERS, NDIS_NIC_SWITCH_FREE_VF_PARAMETERS, NDIS_NIC_SWITCH_FREE_VF_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_NIC_SWITCH_FREE_VF_PARAMETERS, PNDIS_NIC_SWITCH_FREE_VF_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NIC_SWITCH_FREE_VF_PARAMETERS, netvista.ndis_nic_switch_free_vf_parameters, ntddndis/NDIS_NIC_SWITCH_FREE_VF_PARAMETERS, ntddndis/PNDIS_NIC_SWITCH_FREE_VF_PARAMETERS"
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
-	NDIS_NIC_SWITCH_FREE_VF_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_NIC_SWITCH_FREE_VF_PARAMETERS, *PNDIS_NIC_SWITCH_FREE_VF_PARAMETERS
---

# _NDIS_NIC_SWITCH_FREE_VF_PARAMETERS structure


## -description


The <b>NDIS_NIC_SWITCH_FREE_VF_PARAMETERS</b> specifies a PCI Express (PCIe) Virtual Function (VF) whose resources will be freed.


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_NIC_SWITCH_FREE_VF_PARAMETERS</b> structure. This member is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_NIC_SWITCH_FREE_VF_PARAMETERS</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_NIC_SWITCH_FREE_VF_PARAMETERS_REVISION_1

Original version for NDIS 6.30.

Set the <b>Size</b> member to NDIS_SIZEOF_NIC_SWITCH_FREE_VF_PARAMETERS_REVISION_1.


### -field Flags

A ULONG value that contains a bitwise OR of flags. This member is reserved for NDIS.


### -field VFId

An NDIS_SRIOV_FUNCTION_ID value that specifies the unique identifier of the VF on the network adapter.

<div class="alert"><b>Note</b>  Resources for the VF with the specified NDIS_SRIOV_FUNCTION_ID value must have previously been allocated through an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>.

</div>
<div> </div>

## -remarks



 The <b>NDIS_NIC_SWITCH_FREE_VF_PARAMETERS</b> structure is used in OID set requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451822">OID_NIC_SWITCH_FREE_VF</a>.




## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451822">OID_NIC_SWITCH_FREE_VF</a>
 

 

