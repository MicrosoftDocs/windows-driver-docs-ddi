---
UID: NS:ntddndis._NDIS_NIC_SWITCH_VF_INFO_ARRAY
title: "_NDIS_NIC_SWITCH_VF_INFO_ARRAY"
author: windows-driver-content
description: The NDIS_NIC_SWITCH_VF_INFO_ARRAY structure specifies an array. Each element in the array specifies the attributes of a PCI Express (PCIe) virtual functions (VF) that have been enabled and allocated on a network adapter.
old-location: netvista\ndis_nic_switch_vf_info_array.htm
old-project: netvista
ms.assetid: e772eafe-e0c7-4d98-8a9e-7eb56cface37
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PNDIS_NIC_SWITCH_VF_INFO_ARRAY, NDIS_NIC_SWITCH_VF_INFO_ARRAY, NDIS_NIC_SWITCH_VF_INFO_ARRAY structure [Network Drivers Starting with Windows Vista], PNDIS_NIC_SWITCH_VF_INFO_ARRAY, PNDIS_NIC_SWITCH_VF_INFO_ARRAY structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NIC_SWITCH_VF_INFO_ARRAY, netvista.ndis_nic_switch_vf_info_array, ntddndis/NDIS_NIC_SWITCH_VF_INFO_ARRAY, ntddndis/PNDIS_NIC_SWITCH_VF_INFO_ARRAY"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	NDIS_NIC_SWITCH_VF_INFO_ARRAY
product:
- Windows
targetos: Windows
req.typenames: NDIS_NIC_SWITCH_VF_INFO_ARRAY, *PNDIS_NIC_SWITCH_VF_INFO_ARRAY
---

# _NDIS_NIC_SWITCH_VF_INFO_ARRAY structure


## -description


The <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure specifies an array. Each element in the array specifies the attributes of a PCI Express (PCIe) virtual functions (VF) that have been enabled and allocated on a network adapter.


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure. This member is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.

NDIS sets the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure, NDIS sets the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_NIC_SWITCH_VF_INFO_ARRAY_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NIC_SWITCH_VF_INFO_ARRAY_REVISION_1.


### -field Flags

A ULONG value that contains a bitwise OR of the following flags: 





#### NDIS_NIC_SWITCH_VF_INFO_ARRAY_ENUM_ON_SPECIFIC_SWITCH

If this flag is set, the miniport driver must only return an array of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451591">NDIS_NIC_SWITCH_VF_INFO</a> structures for VFs that have been allocated on the network adapter switch specified by the <b>SwitchId</b> member.  For more information, see the Remarks section.

If the Flags member is set to zero, the miniport driver must return an array of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451591">NDIS_NIC_SWITCH_VF_INFO</a> structures for every VF that has been allocated on every network adapter switch of the network adapter.

<div class="alert"><b>Note</b>  Starting with Windows Server 2012, the SR-IOV interface only supports the default network adapter switch on the network adapter. Therefore, the miniport driver must only return an array of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451591">NDIS_NIC_SWITCH_VF_INFO</a> structures for each VF that has been allocated on the default network adapter switch.</div>
<div> </div>

### -field SwitchId

An NDIS_NIC_SWITCH_ID value that specifies a switch identifier. The switch identifier is an integer between zero and the number of switches that the network adapter supports. An NDIS_DEFAULT_SWITCH_ID value indicates the default network adapter switch.



<div class="alert"><b>Note</b>  Starting with Windows Server 2012, the SR-IOV interface only supports the default network adapter switch that is created on the network adapter. Therefore, this member must always be set to NDIS_DEFAULT_SWITCH_ID. </div>
<div> </div>

### -field FirstElementOffset

A ULONG value that specifies the offset, in bytes, to the first element in an array of elements that follow this structure. The offset is measured from the start of the <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure up to the beginning of the first element. Each element in the array is an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451591">NDIS_NIC_SWITCH_VF_INFO</a> structure.



<div class="alert"><b>Note</b>  If <b>NumElements</b> is set to zero, this member is ignored.  </div>
<div> </div>

### -field NumElements

A ULONG value that specifies the number of elements that follow the <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure. 


### -field ElementSize

A ULONG value that specifies the size, in bytes, of each element that follow the <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure.


## -remarks



NDIS returns an <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure when it handles an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451820">OID_NIC_SWITCH_ENUM_VFS</a>.  Each
    element in the array that follows the <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure is an     
    <a href="https://msdn.microsoft.com/library/windows/hardware/hh451591">NDIS_NIC_SWITCH_VF_INFO</a> structure.




## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451591">NDIS_NIC_SWITCH_VF_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451820">OID_NIC_SWITCH_ENUM_VFS</a>
 

 

