---
UID: NS:ntddndis._NDIS_SWITCH_PORT_PARAMETERS
title: _NDIS_SWITCH_PORT_PARAMETERS (ntddndis.h)
description: The NDIS_SWITCH_PORT_PARAMETERS structure contains the configuration data for a Hyper-V extensible switch port.
old-location: netvista\ndis_switch_port_parameters.htm
tech.root: netvista
ms.assetid: E68A9018-1E79-4DA6-8C7A-434A2468169F
ms.date: 05/02/2018
ms.keywords: "*PNDIS_SWITCH_PORT_PARAMETERS, NDIS_SWITCH_PORT_PARAMETERS, NDIS_SWITCH_PORT_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_PORT_PARAMETERS, PNDIS_SWITCH_PORT_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PORT_PARAMETERS, netvista.ndis_switch_port_parameters, ntddndis/NDIS_SWITCH_PORT_PARAMETERS, ntddndis/PNDIS_SWITCH_PORT_PARAMETERS"
ms.topic: struct
f1_keywords:
 - "ntddndis/NDIS_SWITCH_PORT_PARAMETERS"
req.header: ntddndis.h
req.include-header: Ndis.h, Fwpsk.h
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
- ntddndis.h
api_name:
- NDIS_SWITCH_PORT_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_PARAMETERS, *PNDIS_SWITCH_PORT_PARAMETERS
---

# _NDIS_SWITCH_PORT_PARAMETERS structure


## -description


The <b>NDIS_SWITCH_PORT_PARAMETERS</b> structure contains the configuration data for a Hyper-V extensible switch port. 


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PORT_PARAMETERS</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PORT_PARAMETERS</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value:  





#### NDIS_SWITCH_PORT_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_PORT_PARAMETERS_REVISION_1.


### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.




### -field PortId

An NDIS_SWITCH_PORT_ID value that contains the unique identifier of the extensible switch port.


### -field PortName

 An NDIS_SWITCH_PORT_NAME value that specifies the unique internal name of the extensible switch port. 

The internal port name is used by WMI-based policy management applications. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/managing-hyper-v-extensible-switch-extensibility-policies">Managing Hyper-V Extensible Switch Policies</a>.


### -field PortFriendlyName

 An NDIS_SWITCH_PORT_FRIENDLYNAME value that specifies the user-friendly description of the extensible switch port.


### -field PortType

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_switch_port_type">NDIS_SWITCH_PORT_TYPE</a> value that specifies the type of the extensible switch port.


### -field IsValidationPort

 If TRUE, indicates a port that is temporarily created for test and validation purposes before a VM network adapter connection is established. For more information about this port type, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/validation-ports">Validation Ports</a>.


### -field PortState

 An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_switch_port_state">NDIS_SWITCH_PORT_STATE</a> value that specifies the current state of the port. 


## -remarks



The <b>InformationBuffer</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>  structure contains a pointer to an <b>NDIS_SWITCH_PORT_PARAMETERS</b> structure for the following OID requests:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-create">OID_SWITCH_PORT_CREATE</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-updated">OID_SWITCH_PORT_UPDATED</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-delete">OID_SWITCH_PORT_DELETE</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-teardown">OID_SWITCH_PORT_TEARDOWN</a>


</li>
</ul>
OID query requests of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-array">OID_SWITCH_PORT_ARRAY</a> return an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_array">NDIS_SWITCH_PORT_ARRAY</a> structure that contains an array of elements. Each element is formatted as an <b>NDIS_SWITCH_PORT_PARAMETERS</b> structure.

Extensible switch extensions can access the  port property buffer inside an <b>NDIS_SWITCH_PORT_PARAMETERS</b> structure by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-switch-port-at-array-index">NDIS_SWITCH_PORT_AT_ARRAY_INDEX</a> macro.

<div class="alert"><b>Note</b>  The <b>NDIS_SWITCH_PORT_NAME</b> and  <b>NDIS_SWITCH_PORT_FRIENDLYNAME</b> data types are type-defined by the <a href="https://docs.microsoft.com/windows/desktop/api/ifdef/ns-ifdef-_if_counted_string_lh">IF_COUNTED_STRING</a> structure. A string that is defined by this structure does not have to be null-terminated. However, the length of the string must be set in the <b>Length</b> member of this structure. If the string is null-terminated, the <b>Length</b> member must not include the terminating null character.

</div>
<div> </div>



## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows/desktop/api/ifdef/ns-ifdef-_if_counted_string_lh">IF_COUNTED_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_array">NDIS_SWITCH_PORT_ARRAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-switch-port-at-array-index">NDIS_SWITCH_PORT_AT_ARRAY_INDEX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_parameters">NDIS_SWITCH_PORT_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_switch_port_state">NDIS_SWITCH_PORT_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_switch_port_type">NDIS_SWITCH_PORT_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-array">OID_SWITCH_PORT_ARRAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-create">OID_SWITCH_PORT_CREATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-delete">OID_SWITCH_PORT_DELETE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-teardown">OID_SWITCH_PORT_TEARDOWN</a>
 

 

