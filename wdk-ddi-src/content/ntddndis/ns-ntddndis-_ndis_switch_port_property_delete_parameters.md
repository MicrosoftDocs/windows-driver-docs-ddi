---
UID: NS:ntddndis._NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS
title: "_NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS"
author: windows-driver-content
description: The NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS structure specifies the parameters for a Hyper-V extensible switch port policy property that will be deleted.
old-location: netvista\ndis_switch_port_property_delete_parameters.htm
tech.root: netvista
ms.assetid: 92ef7d1a-2ede-4bbb-87bd-dcad53c25ea7
ms.date: 05/02/2018
ms.keywords: "*PNDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS, NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS, NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS, PNDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS, netvista.ndis_switch_port_property_delete_parameters, ntddndis/NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS, ntddndis/PNDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS, *PNDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS
---

# _NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS structure


## -description


The <b>NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS</b> structure specifies the parameters for a Hyper-V extensible switch port policy property that will be deleted. 


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS</b> structure. This member is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value:  





#### NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS_REVISION_1.


### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


### -field PortId

 An NDIS_SWITCH_PORT_ID value that contains the unique identifier of the extensible switch port to which the property is assigned.


### -field PropertyType

 An <a href="https://msdn.microsoft.com/library/windows/hardware/hh598242">NDIS_SWITCH_PORT_PROPERTY_TYPE</a> enumeration value that specifies the type of port property that will be deleted.


### -field PropertyId

A GUID value that identifies the property for the extensible switch port.




### -field PropertyInstanceId

An NDIS_SWITCH_OBJECT_INSTANCE_ID value that specifies the instance identifier for the extensible switch port property.




## -remarks



The <b>NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS</b> structure is used in OID set requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598276">OID_SWITCH_PORT_PROPERTY_DELETE</a>.

For more information about extensible switch policies, see <a href="https://msdn.microsoft.com/8AB85E48-EF37-4D42-873B-34D4835AF22E">Hyper-V Extensible Switch Policies</a>.




## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598242">NDIS_SWITCH_PORT_PROPERTY_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598276">OID_SWITCH_PORT_PROPERTY_DELETE</a>
 

 

