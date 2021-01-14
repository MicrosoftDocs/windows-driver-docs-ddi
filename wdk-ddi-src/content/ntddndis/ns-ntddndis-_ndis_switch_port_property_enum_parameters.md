---
UID: NS:ntddndis._NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS
title: _NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS (ntddndis.h)
description: The NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS structure specifies an array of policy properties for a Hyper-V extensible switch port. Each element in the array is formatted as an NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO structure.
old-location: netvista\ndis_switch_port_property_enum_parameters.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS structure"]
ms.keywords: "*PNDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS, NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS, NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS, PNDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS, netvista.ndis_switch_port_property_enum_parameters, ntddndis/NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS, ntddndis/PNDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS"
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
req.typenames: NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS, *PNDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS
f1_keywords:
 - _NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS
 - ntddndis/_NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS
 - PNDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS
 - ntddndis/PNDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS
 - NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS
 - ntddndis/NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - _NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS
 - PNDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS
 - NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS
---

# _NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS structure


## -description

The <b>NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS</b> structure specifies an array of policy properties for a Hyper-V extensible switch port. Each element in the array is formatted as an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_enum_info">NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO</a> structure.

## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS</b> structure. This member is formatted as an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value:





#### NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS_REVISION_1.

### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.

### -field PortId

 An NDIS_SWITCH_PORT_ID value that contains the unique identifier of the extensible switch port for which properties are enumerated.

### -field PropertyType

 An <a href="/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_switch_port_property_type">NDIS_SWITCH_PORT_PROPERTY_TYPE</a> enumeration value that specifies the port property type. When an OID method request of <a href="/windows-hardware/drivers/network/oid-switch-port-property-enum">OID_SWITCH_PORT_PROPERTY_ENUM</a> is issued, the extensible switch extension returns port properties that match this property type.

### -field PropertyId

A GUID value that identifies the property for the extensible switch port.

### -field SerializationVersion

An NDIS_SWITCH_OBJECT_SERIALIZATION_VERSION value that identifies the format version of the serialized port property data. This data is serialized for access by the extension from the Managed Object Format (MOF) file that defined the property.

<div class="alert"><b>Note</b>  For Windows Server 2012, the <b>SerializationVersion</b> member must be set to NDIS_SWITCH_OBJECT_SERIALIZATION_VERSION_1.</div>
<div> </div>

### -field FirstPropertyOffset

A USHORT value that specifies the offset, in bytes, to the first <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_enum_info">NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO</a> element that follows the <b>NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS</b> structure. The offset is measured from the start of the <b>NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS</b> structure up to the beginning of the first element of the array.

<div class="alert"><b>Note</b>  If the value of <b>NumProperties</b> is zero, this member is ignored. </div>
<div> </div>

### -field NumProperties

A ULONG value that specifies the number of <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_enum_info">NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO</a> elements that follow the <b>NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS</b> structure.

### -field Reserved

Reserved for future use.

## -remarks

The <b>NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS</b> structure is used in OID method requests of <a href="/windows-hardware/drivers/network/oid-switch-port-property-enum">OID_SWITCH_PORT_PROPERTY_ENUM</a>. An array of <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_enum_info">NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO</a> structures follow the <b>NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS</b> structure in the information buffer that is associated with these OID set requests. The <b>InformationBuffer</b> member of the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure contains a pointer to this information buffer.

Extensible switch extensions can access the first <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_enum_info">NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO</a> structure that is specified by the  <b>NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS</b> structure by using the <a href="/windows-hardware/drivers/network/ndis-switch-port-property-enum-parameters-get-first-info">NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO</a> macro.

For more information about extensible switch policies, see <a href="/windows-hardware/drivers/network/hyper-v-extensible-switch-policies">Hyper-V Extensible Switch Policies</a>.

## -see-also

<b></b>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_enum_info">NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO</a>



<a href="/windows-hardware/drivers/network/ndis-switch-port-property-enum-parameters-get-first-info">NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO</a>



<a href="/windows-hardware/drivers/network/oid-switch-port-property-enum">OID_SWITCH_PORT_PROPERTY_ENUM</a>

