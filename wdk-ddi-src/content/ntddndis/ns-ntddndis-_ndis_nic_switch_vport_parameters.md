---
UID: NS:ntddndis._NDIS_NIC_SWITCH_VPORT_PARAMETERS
title: "_NDIS_NIC_SWITCH_VPORT_PARAMETERS"
author: windows-driver-content
description: The NDIS_NIC_SWITCH_VPORT_PARAMETERS structure specifies the configuration for a virtual port (VPort) on a network adapter switch of the network adapter.
old-location: netvista\ndis_nic_switch_vport_parameters.htm
tech.root: netvista
ms.assetid: d75bec3d-b427-40d2-bec3-95b7409f31bb
ms.date: 5/2/2018
ms.keywords: "*PNDIS_NIC_SWITCH_VPORT_PARAMETERS, NDIS_NIC_SWITCH_VPORT_PARAMETERS, NDIS_NIC_SWITCH_VPORT_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_NIC_SWITCH_VPORT_PARAMETERS, PNDIS_NIC_SWITCH_VPORT_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NIC_SWITCH_VPORT_PARAMETERS, netvista.ndis_nic_switch_vport_parameters, ntddndis/NDIS_NIC_SWITCH_VPORT_PARAMETERS, ntddndis/PNDIS_NIC_SWITCH_VPORT_PARAMETERS"
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
-	NDIS_NIC_SWITCH_VPORT_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_NIC_SWITCH_VPORT_PARAMETERS, *PNDIS_NIC_SWITCH_VPORT_PARAMETERS
---

# _NDIS_NIC_SWITCH_VPORT_PARAMETERS structure


## -description


The <b>NDIS_NIC_SWITCH_VPORT_PARAMETERS</b> structure specifies the configuration for a virtual port (VPort) on a network adapter switch of the network adapter. 


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_NIC_SWITCH_VPORT_PARAMETERS</b> structure. This member is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_NIC_SWITCH_VPORT_PARAMETERS</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_NIC_SWITCH_VPORT_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NIC_SWITCH_VPORT_PARAMETERS_REVISION_1.


### -field Flags

 A ULONG value that contains a bitwise OR of flags. The following flags are defined for this member. 






#### NDIS_NIC_SWITCH_VPORT_PARAMS_LOOKAHEAD_SPLIT_ENABLED


	                                 
	This flag is reserved for future use. 
Miniport drivers must ignore this flag.



#### NDIS_NIC_SWITCH_VPORT_PARAMS_FLAGS_CHANGED

This flag specifies that the <b>Flags</b> member has been updated after the VPort has been created. These flags can be enabled or disabled after the VPort has been created by using an OID set request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451825">OID_NIC_SWITCH_VPORT_PARAMETERS</a>. 


<div class="alert"><b>Note</b>  This flag is valid only when this structure is used in OID set requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451825">OID_NIC_SWITCH_VPORT_PARAMETERS</a>. </div>
<div> </div>


#### NDIS_NIC_SWITCH_VPORT_PARAMS_NAME_CHANGED

                                  
This flag specifies that the <b>VPortName</b> member has been updated after the VPort has been created. This member can be updated by using an OID set request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451825">OID_NIC_SWITCH_VPORT_PARAMETERS</a>. 


<div class="alert"><b>Note</b>  This flag is valid only when this structure is used in OID set requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451825">OID_NIC_SWITCH_VPORT_PARAMETERS</a>. </div>
<div> </div>


#### NDIS_NIC_SWITCH_VPORT_PARAMS_INT_MOD_CHANGED

This flag specifies that the <b>InterruptModeration</b> member has been updated after the VPort has been created. This member can be updated by using an OID set request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451825">OID_NIC_SWITCH_VPORT_PARAMETERS</a>. 
 


<div class="alert"><b>Note</b>  This flag is valid only when this structure is used in OID set requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451825">OID_NIC_SWITCH_VPORT_PARAMETERS</a>. </div>
<div> </div>


#### NDIS_NIC_SWITCH_VPORT_PARAMS_STATE_CHANGED

This flag specifies that the <b>VPortState</b> member has been updated after the VPort has been created. This member can be updated by using an OID set request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451825">OID_NIC_SWITCH_VPORT_PARAMETERS</a>.

<div class="alert"><b>Note</b>  This flag is valid only when this structure is used in OID set requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451825">OID_NIC_SWITCH_VPORT_PARAMETERS</a>. </div>
<div> </div>


#### NDIS_NIC_SWITCH_VPORT_PARAMS_PROCESSOR_AFFINITY_CHANGED

This flag specifies that the <b>ProcessoryAffinity</b> member has been updated after the VPort has been created. The processor affinity of a VPort can only be updated if the VPort is attached to the PF on the network adapter. The <b>ProcessoryAffinity</b> member can be updated by using an OID set request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451825">OID_NIC_SWITCH_VPORT_PARAMETERS</a>.

<div class="alert"><b>Note</b>  This flag is valid only when this structure is used in OID set requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451825">OID_NIC_SWITCH_VPORT_PARAMETERS</a>. </div>
<div> </div>

### -field SwitchId

An NDIS_NIC_SWITCH_ID value that specifies the identifier of the switch on which the VPort is to be created.

The switch identifier is an integer between zero and the number of switches that the network adapter supports. An NDIS_DEFAULT_SWITCH_ID value indicates the default network adapter switch.



<div class="alert"><b>Note</b>  Starting with Windows Server 2012, the single root I/O virtualization (SR-IOV) interface only supports the default network adapter switch on the network adapter. The value of this member must be set to NDIS_DEFAULT_SWITCH_ID. </div>
<div> </div>

### -field VPortId

An NDIS_NIC_SWITCH_VPORT_ID value that specifies the identifier of a VPort  on the network adapter. The value is allocated by NDIS,  and is unique across the network adapter. 

The <b>VPortId</b> value is within the range from zero to (<b>NumVPorts</b> - 1), where <b>NumVPorts</b> is the number of VPorts that the miniport driver has configured on the network adapter. The driver specifies this number in the <b>NumVPorts</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451582">NDIS_NIC_SWITCH_INFO</a> structure. The driver returns this structure through an OID query request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451819">OID_NIC_SWITCH_ENUM_SWITCHES</a>. 


<div class="alert"><b>Note</b>  A VPort identifier of NDIS_DEFAULT_VPORT_ID is reserved for the default VPort that is attached to the PF on the default NIC switch.</div>
<div> </div>

### -field VPortName

An NDIS_VPORT_NAME value that specifies the name of the VPort. This member contains a user-friendly description of the VPort.




### -field AttachedFunctionId

An NDIS_SRIOV_FUNCTION_ID value that specifies the ID of the Physical Function (PF) or Virtual Function (VF) that the VPort is attached to. A value of NDIS_PF_FUNCTION_ID specifies that the VPort is attached to the PF. If the value is a valid VF identifier, the VPort is attached to the VF. 


### -field NumQueuePairs

A ULONG value that specifies the number of queue pairs configured for this VPort.

A queue pair consists of a transmit queue and receive queue. Queue pairs associated with the default VPort are configured at the time of switch creation through an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451815">OID_NIC_SWITCH_CREATE_SWITCH</a>.
One or more queue pairs are configured on a nondefault VPort through an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451816">OID_NIC_SWITCH_CREATE_VPORT</a>.



### -field InterruptModeration

An <a href="https://msdn.microsoft.com/library/windows/hardware/hh451596">NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION</a> value that specifies the interrupt moderation setting of the VPort.




### -field VPortState

An <a href="https://msdn.microsoft.com/library/windows/hardware/hh451598">NDIS_NIC_SWITCH_VPORT_STATE</a> value that specifies the current state of the VPort.


### -field ProcessorAffinity

A GROUP_AFFINITY value that specifies the group number and a bitmap of the CPUs that this VPort is associated with. This field is valid only for VPorts that are attached to the PF. 

<div class="alert"><b>Note</b>  For nondefault PF VPorts, a GROUP_AFFINITY value that specifies only one processor must be specified when the VPort is created. VPorts are created through an OID method request of  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451816">OID_NIC_SWITCH_CREATE_VPORT</a>.</div>
<div> </div>
The processor affinity associated with the nondefault VPort attached to the PF can be changed after VPort creation. The processor affinity associated with the default VPort can also be changed by using an OID set request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451825">OID_NIC_SWITCH_VPORT_PARAMETERS</a>.




### -field LookaheadSize

This member is reserved for future use. This member must be set to zero.


### -field NdkParams

 


### -field QosSqId

 




## -remarks



This structure is used in OID requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451816">OID_NIC_SWITCH_CREATE_VPORT</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh451825">OID_NIC_SWITCH_VPORT_PARAMETERS</a>.

For more information about the SR-IOV interface, see 	<a href="https://msdn.microsoft.com/B241F468-F568-4500-9356-E576CEBA8F3B">Overview of Single Root I/O Virtualization (SR-IOV)</a>.




## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451582">NDIS_NIC_SWITCH_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451591">NDIS_NIC_SWITCH_VF_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451816">OID_NIC_SWITCH_CREATE_VPORT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451819">OID_NIC_SWITCH_ENUM_SWITCHES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451825">OID_NIC_SWITCH_VPORT_PARAMETERS</a>
 

 

