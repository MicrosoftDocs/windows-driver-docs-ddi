---
UID: NS:ntddndis._NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS
title: _NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS (ntddndis.h)
description: The NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS structure specifies the parameters for a Hyper-V extensible switch profile property that will be deleted.
old-location: netvista\ndis_switch_property_delete_parameters.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS structure"]
ms.keywords: "*PNDIS_SWITCH_PROPERTY_DELETE_PARAMETERS, NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS, NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_PROPERTY_DELETE_PARAMETERS, PNDIS_SWITCH_PROPERTY_DELETE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS, netvista.ndis_switch_property_delete_parameters, ntddndis/NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS, ntddndis/PNDIS_SWITCH_PROPERTY_DELETE_PARAMETERS"
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
req.typenames: NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS, *PNDIS_SWITCH_PROPERTY_DELETE_PARAMETERS
f1_keywords:
 - _NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS
 - ntddndis/_NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS
 - PNDIS_SWITCH_PROPERTY_DELETE_PARAMETERS
 - ntddndis/PNDIS_SWITCH_PROPERTY_DELETE_PARAMETERS
 - NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS
 - ntddndis/NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS
---

# _NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS structure


## -description

The <b>NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS</b> structure specifies the parameters for a Hyper-V extensible switch profile property that will be deleted.

## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS</b> structure. This member is formatted as an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value:





#### NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS_REVISION_1.

### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.

### -field PropertyType

 An <a href="/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_switch_property_type">NDIS_SWITCH_PROPERTY_TYPE</a> enumeration value that specifies the type of extensible switch property that will be deleted.

### -field PropertyId

A GUID value that identifies the property for the extensible switch.

### -field PropertyInstanceId

An NDIS_SWITCH_OBJECT_INSTANCE_ID value that specifies the instance identifier of the  extensible switch property.

## -remarks

The <b>NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS</b> structure is used in OID set requests of <a href="/windows-hardware/drivers/network/oid-switch-property-delete">OID_SWITCH_PROPERTY_DELETE</a>.

For more information about extensible switch policies, see <a href="/windows-hardware/drivers/network/hyper-v-extensible-switch-policies">Hyper-V Extensible Switch Policies</a>.

## -see-also

<b></b>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_switch_property_type">NDIS_SWITCH_PROPERTY_TYPE</a>



<a href="/windows-hardware/drivers/network/oid-switch-property-delete">OID_SWITCH_PROPERTY_DELETE</a>
