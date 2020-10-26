---
UID: NS:ntddndis._NDIS_NIC_SWITCH_VPORT_PARAMETERS
title: _NDIS_NIC_SWITCH_VPORT_PARAMETERS (ntddndis.h)
description: The NDIS_NIC_SWITCH_VPORT_PARAMETERS structure specifies the configuration for a virtual port (VPort) on a network adapter switch of the network adapter.
old-location: netvista\ndis_nic_switch_vport_parameters.htm
tech.root: netvista
ms.assetid: d75bec3d-b427-40d2-bec3-95b7409f31bb
ms.date: 10/30/2020
keywords: ["NDIS_NIC_SWITCH_VPORT_PARAMETERS structure"]
ms.keywords: "*PNDIS_NIC_SWITCH_VPORT_PARAMETERS, NDIS_NIC_SWITCH_VPORT_PARAMETERS, NDIS_NIC_SWITCH_VPORT_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_NIC_SWITCH_VPORT_PARAMETERS, PNDIS_NIC_SWITCH_VPORT_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NIC_SWITCH_VPORT_PARAMETERS, netvista.ndis_nic_switch_vport_parameters, ntddndis/NDIS_NIC_SWITCH_VPORT_PARAMETERS, ntddndis/PNDIS_NIC_SWITCH_VPORT_PARAMETERS"
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
targetos: Windows
req.typenames: NDIS_NIC_SWITCH_VPORT_PARAMETERS, *PNDIS_NIC_SWITCH_VPORT_PARAMETERS
f1_keywords:
 - _NDIS_NIC_SWITCH_VPORT_PARAMETERS
 - ntddndis/_NDIS_NIC_SWITCH_VPORT_PARAMETERS
 - PNDIS_NIC_SWITCH_VPORT_PARAMETERS
 - ntddndis/PNDIS_NIC_SWITCH_VPORT_PARAMETERS
 - NDIS_NIC_SWITCH_VPORT_PARAMETERS
 - ntddndis/NDIS_NIC_SWITCH_VPORT_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_NIC_SWITCH_VPORT_PARAMETERS
---

# _NDIS_NIC_SWITCH_VPORT_PARAMETERS structure


## -description

The **NDIS_NIC_SWITCH_VPORT_PARAMETERS** structure specifies the configuration for a virtual port (VPort) on a network adapter switch of the network adapter.

## -struct-fields

### -field Header

The type, revision, and size of the **NDIS_NIC_SWITCH_VPORT_PARAMETERS** structure. This member is formatted as an [NDIS_OBJECT_HEADER](ns-ntddndis-_ndis_object_header.md) structure.

The miniport driver must set the **Type** member of **Header** to NDIS_OBJECT_TYPE_DEFAULT. 

To indicate the version of the **NDIS_NIC_SWITCH_VPORT_PARAMETERS** structure, set the **Revision** member of **Header** to one of the following values:

#### NDIS_NIC_SWITCH_VPORT_PARAMETERS_REVISION_2

Added the **QosSqId** field for NDIS 6.50.

Set the **Size** member to NDIS_SIZEOF_NIC_SWITCH_VPORT_PARAMETERS_REVISION_2.

#### NDIS_NIC_SWITCH_VPORT_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NIC_SWITCH_VPORT_PARAMETERS_REVISION_1.

### -field Flags

A ULONG value that contains a bitwise OR of flags. The following flags are defined for this member. 


#### NDIS_NIC_SWITCH_VPORT_PARAMS_LOOKAHEAD_SPLIT_ENABLED

This flag is reserved for future use. 
Miniport drivers must ignore this flag.


#### NDIS_NIC_SWITCH_VPORT_PARAMS_FLAGS_CHANGED

This flag specifies that the **Flags** member has been updated after the VPort has been created. These flags can be enabled or disabled after the VPort has been created by using an OID set request of [OID_NIC_SWITCH_VPORT_PARAMETERS](/windows-hardware/drivers/network/oid-nic-switch-vport-parameters). 


> [!NOTE]
> This flag is valid only when this structure is used in OID set requests of [OID_NIC_SWITCH_VPORT_PARAMETERS](/windows-hardware/drivers/network/oid-nic-switch-vport-parameters).


#### NDIS_NIC_SWITCH_VPORT_PARAMS_NAME_CHANGED

This flag specifies that the **VPortName** member has been updated after the VPort has been created. This member can be updated by using an OID set request of [OID_NIC_SWITCH_VPORT_PARAMETERS](/windows-hardware/drivers/network/oid-nic-switch-vport-parameters). 


> [!NOTE]
> This flag is valid only when this structure is used in OID set requests of [OID_NIC_SWITCH_VPORT_PARAMETERS](/windows-hardware/drivers/network/oid-nic-switch-vport-parameters).


#### NDIS_NIC_SWITCH_VPORT_PARAMS_INT_MOD_CHANGED

This flag specifies that the **InterruptModeration** member has been updated after the VPort has been created. This member can be updated by using an OID set request of [OID_NIC_SWITCH_VPORT_PARAMETERS](/windows-hardware/drivers/network/oid-nic-switch-vport-parameters). 
 
> [!NOTE]
> This flag is valid only when this structure is used in OID set requests of [OID_NIC_SWITCH_VPORT_PARAMETERS](/windows-hardware/drivers/network/oid-nic-switch-vport-parameters).


#### NDIS_NIC_SWITCH_VPORT_PARAMS_STATE_CHANGED

This flag specifies that the **VPortState** member has been updated after the VPort has been created. This member can be updated by using an OID set request of [OID_NIC_SWITCH_VPORT_PARAMETERS](/windows-hardware/drivers/network/oid-nic-switch-vport-parameters).

> [!NOTE]
> This flag is valid only when this structure is used in OID set requests of [OID_NIC_SWITCH_VPORT_PARAMETERS](/windows-hardware/drivers/network/oid-nic-switch-vport-parameters).


#### NDIS_NIC_SWITCH_VPORT_PARAMS_PROCESSOR_AFFINITY_CHANGED

This flag specifies that the **ProcessoryAffinity** member has been updated after the VPort has been created. The processor affinity of a VPort can only be updated if the VPort is attached to the PF on the network adapter. The **ProcessoryAffinity** member can be updated by using an OID set request of [OID_NIC_SWITCH_VPORT_PARAMETERS](/windows-hardware/drivers/network/oid-nic-switch-vport-parameters).

> [!NOTE]
> This flag is valid only when this structure is used in OID set requests of [OID_NIC_SWITCH_VPORT_PARAMETERS](/windows-hardware/drivers/network/oid-nic-switch-vport-parameters).

### -field SwitchId

An NDIS_NIC_SWITCH_ID value that specifies the identifier of the switch on which the VPort is to be created.

The switch identifier is an integer between zero and the number of switches that the network adapter supports. An NDIS_DEFAULT_SWITCH_ID value indicates the default network adapter switch.



> [!NOTE]
> Starting with Windows Server 2012, the single root I/O virtualization (SR-IOV) interface only supports the default network adapter switch on the network adapter. The value of this member must be set to NDIS_DEFAULT_SWITCH_ID.

### -field VPortId

An NDIS_NIC_SWITCH_VPORT_ID value that specifies the identifier of a VPort  on the network adapter. The value is allocated by NDIS,  and is unique across the network adapter. 

The **VPortId** value is within the range from zero to (**NumVPorts** - 1), where **NumVPorts** is the number of VPorts that the miniport driver has configured on the network adapter. The driver specifies this number in the **NumVPorts** member of the [NDIS_NIC_SWITCH_INFO](/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_nic_switch_info) structure. The driver returns this structure through an OID query request of [OID_NIC_SWITCH_ENUM_SWITCHES](/windows-hardware/drivers/network/oid-nic-switch-enum-switches). 


> [!NOTE]
> A VPort identifier of NDIS_DEFAULT_VPORT_ID is reserved for the default VPort that is attached to the PF on the default NIC switch.

### -field VPortName

An NDIS_VPORT_NAME value that specifies the name of the VPort. This member contains a user-friendly description of the VPort.

### -field AttachedFunctionId

An NDIS_SRIOV_FUNCTION_ID value that specifies the ID of the Physical Function (PF) or Virtual Function (VF) that the VPort is attached to. A value of NDIS_PF_FUNCTION_ID specifies that the VPort is attached to the PF. If the value is a valid VF identifier, the VPort is attached to the VF.

### -field NumQueuePairs

A ULONG value that specifies the number of queue pairs configured for this VPort.

A queue pair consists of a transmit queue and receive queue. Queue pairs associated with the default VPort are configured at the time of switch creation through an OID method request of [OID_NIC_SWITCH_CREATE_SWITCH](/windows-hardware/drivers/network/oid-nic-switch-create-switch).
One or more queue pairs are configured on a nondefault VPort through an OID method request of [OID_NIC_SWITCH_CREATE_VPORT](/windows-hardware/drivers/network/oid-nic-switch-create-vport).

### -field InterruptModeration

An [NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION](/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_nic_switch_vport_interrupt_moderation) value that specifies the interrupt moderation setting of the VPort.

### -field VPortState

An [NDIS_NIC_SWITCH_VPORT_STATE](/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_nic_switch_vport_state) value that specifies the current state of the VPort.

### -field ProcessorAffinity

A GROUP_AFFINITY value that specifies the group number and a bitmap of the CPUs that this VPort is associated with. This field is valid only for VPorts that are attached to the PF. 

> [!NOTE]
> For nondefault PF VPorts, a GROUP_AFFINITY value that specifies only one processor must be specified when the VPort is created. VPorts are created through an OID method request of [OID_NIC_SWITCH_CREATE_VPORT](/windows-hardware/drivers/network/oid-nic-switch-create-vport).

The processor affinity associated with the nondefault VPort attached to the PF can be changed after VPort creation. The processor affinity associated with the default VPort can also be changed by using an OID set request of [OID_NIC_SWITCH_VPORT_PARAMETERS](/windows-hardware/drivers/network/oid-nic-switch-vport-parameters).

### -field LookaheadSize

This member is reserved for future use. This member must be set to zero.

### -field NdkParams

### -field QosSqId

Associates a vPort with a Scheduler Queue (SQ). Set this field to a valid SQ ID to associate the vPort to an SQ. Set this field to **zero** if there is no SQ association.

## -remarks

This structure is used in OID requests of [OID_NIC_SWITCH_CREATE_VPORT](/windows-hardware/drivers/network/oid-nic-switch-create-vport) and [OID_NIC_SWITCH_VPORT_PARAMETERS](/windows-hardware/drivers/network/oid-nic-switch-vport-parameters).

For more information about the SR-IOV interface, see [Overview of Single Root I/O Virtualization (SR-IOV)](/windows-hardware/drivers/network/overview-of-single-root-i-o-virtualization--sr-iov-).

## -see-also

[NDIS_NIC_SWITCH_INFO](/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_nic_switch_info)

[NDIS_NIC_SWITCH_VF_INFO](/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_nic_switch_vf_info)

[NDIS_OBJECT_HEADER](/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header)

[OID_NIC_SWITCH_CREATE_VPORT](/windows-hardware/drivers/network/oid-nic-switch-create-vport)

[OID_NIC_SWITCH_ENUM_SWITCHES](/windows-hardware/drivers/network/oid-nic-switch-enum-switches)

[OID_NIC_SWITCH_VPORT_PARAMETERS](/windows-hardware/drivers/network/oid-nic-switch-vport-parameters)

