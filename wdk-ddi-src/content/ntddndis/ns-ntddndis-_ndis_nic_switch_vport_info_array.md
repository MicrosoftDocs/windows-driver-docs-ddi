---
UID: NS:ntddndis._NDIS_NIC_SWITCH_VPORT_INFO_ARRAY
title: "_NDIS_NIC_SWITCH_VPORT_INFO_ARRAY"
author: windows-driver-content
description: The NDIS_NIC_SWITCH_VPORT_INFO_ARRAY structure specifies an array. Each element in the array specifies the attributes of a virtual port (VPort) that has been created on a network adapter's network adapter switch.
old-location: netvista\ndis_nic_switch_vport_info_array.htm
old-project: netvista
ms.assetid: 64bb0edf-b281-40cc-b36e-6ae1fb71ccb4
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PNDIS_NIC_SWITCH_VPORT_INFO_ARRAY, NDIS_NIC_SWITCH_VPORT_INFO_ARRAY, NDIS_NIC_SWITCH_VPORT_INFO_ARRAY structure [Network Drivers Starting with Windows Vista], PNDIS_NIC_SWITCH_VPORT_INFO_ARRAY, PNDIS_NIC_SWITCH_VPORT_INFO_ARRAY structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NIC_SWITCH_VPORT_INFO_ARRAY, netvista.ndis_nic_switch_vport_info_array, ntddndis/NDIS_NIC_SWITCH_VPORT_INFO_ARRAY, ntddndis/PNDIS_NIC_SWITCH_VPORT_INFO_ARRAY"
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
-	NDIS_NIC_SWITCH_VPORT_INFO_ARRAY
product: Windows
targetos: Windows
req.typenames: NDIS_NIC_SWITCH_VPORT_INFO_ARRAY, *PNDIS_NIC_SWITCH_VPORT_INFO_ARRAY
---

# _NDIS_NIC_SWITCH_VPORT_INFO_ARRAY structure


## -description


The <b>NDIS_NIC_SWITCH_VPORT_INFO_ARRAY</b> structure specifies an array. Each element in the array specifies the attributes of a virtual port (VPort) that has been created on a network adapter's network adapter switch. 


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_NIC_SWITCH_VPORT_INFO_ARRAY</b> structure. This member is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.

NDIS sets the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_NIC_SWITCH_VPORT_INFO_ARRAY</b> structure, NDIS sets the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_NIC_SWITCH_VPORT_INFO_ARRAY_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NIC_SWITCH_VPORT_INFO_ARRAY_REVISION_1.


### -field Flags

A ULONG value that contains a bitwise OR of the following flags: 





#### NDIS_NIC_SWITCH_VPORT_INFO_ARRAY_ENUM_ON_SPECIFIC_FUNCTION

This flag specifies to enumerate the VPorts attached to a specific PCI Express (PCIe) function. The function is specified in the <b>AttachedFunctionId</b> member. This flag can be used to enumerate the VPorts attached to the PCIe Physical Function (PF) or a specified PCIe Virtual Function (VF).



#### NDIS_NIC_SWITCH_VPORT_INFO_ARRAY_ENUM_ON_SPECIFIC_SWITCH

This flag specifies to enumerate the VPorts created on a specific switch, specified by the SwitchId. This enumerates all the VPorts created on the switch.

<div class="alert"><b>Note</b>  These flags are mutually exclusive. Only one flag can be set in the <b>Flags</b> member.</div>
<div> </div>

### -field SwitchId

An NDIS_NIC_SWITCH_ID value that specifies a switch identifier. The switch identifier is an integer between zero and the number of switches that the network adapter supports. An NDIS_DEFAULT_SWITCH_ID value indicates the default network adapter switch.



The <b>SwitchId</b> member is only valid  if NDIS_NIC_SWITCH_VPORT_INFO_ARRAY_ENUM_ON_SPECIFIC_SWITCH is specified in the <b>Flags</b> member. 

<div class="alert"><b>Note</b>  Starting with Windows Server 2012, the single root I/O virtualization (SR-IOV) interface only supports the default network adapter switch on the network adapter. The value of this member must be set to NDIS_DEFAULT_SWITCH_ID. </div>
<div> </div>

### -field AttachedFunctionId

An NDIS_SRIOV_FUNCTION_ID value that specifies the identifier of the PF or a VF on the network adapter.

<div class="alert"><b>Note</b>  If this value is NDIS_PF_FUNCTION_ID, the VPort is attached to the PF.</div>
<div> </div>
The <b>AttachedFunctionId</b> member is only valid  if NDIS_NIC_SWITCH_VPORT_INFO_ARRAY_ENUM_ON_SPECIFIC_FUNCTION is specified in the <b>Flags</b> member. 


### -field FirstElementOffset

A ULONG value that specifies the offset, in bytes, to the first element in an array of elements that follow this structure. The offset is measured from the start of the <b>NDIS_NIC_SWITCH_VPORT_INFO_ARRAY</b> structure up to the beginning of the first element. Each element in the array is an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451594">NDIS_NIC_SWITCH_VPORT_INFO</a> structure.



<div class="alert"><b>Note</b>  If <b>NumElements</b> is set to zero, this member is ignored.  </div>
<div> </div>

### -field NumElements

A ULONG value that specifies the number of elements that follow the <b>NDIS_NIC_SWITCH_VPORT_INFO_ARRAY</b> structure. 


### -field ElementSize

A ULONG value that specifies the size, in bytes, of each element that follows the <b>NDIS_NIC_SWITCH_VPORT_INFO_ARRAY</b> structure.


## -remarks



NDIS returns an <b>NDIS_NIC_SWITCH_VPORT_INFO_ARRAY</b> structure when NDIS handles an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451821">OID_NIC_SWITCH_ENUM_VPORTS</a>.  Each
    element in the array that follows the <b>NDIS_NIC_SWITCH_VPORT_INFO_ARRAY</b> structure is an 
    
    <a href="https://msdn.microsoft.com/library/windows/hardware/hh451594">NDIS_NIC_SWITCH_VPORT_INFO</a> structure.

For more information about the SR-IOV interface, see 	<a href="https://msdn.microsoft.com/B241F468-F568-4500-9356-E576CEBA8F3B">Overview of Single Root I/O Virtualization (SR-IOV)</a>.




## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451594">NDIS_NIC_SWITCH_VPORT_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451821">OID_NIC_SWITCH_ENUM_VPORTS</a>
 

 

