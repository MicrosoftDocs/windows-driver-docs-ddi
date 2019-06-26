---
UID: NS:ntddndis._NDIS_SWITCH_PORT_PROPERTY_CUSTOM
title: _NDIS_SWITCH_PORT_PROPERTY_CUSTOM (ntddndis.h)
description: The NDIS_SWITCH_PORT_PROPERTY_CUSTOM structure specifies a custom policy property for a Hyper-V extensible switch port.
old-location: netvista\ndis_switch_port_property_custom.htm
tech.root: netvista
ms.assetid: 5ac17c34-c71c-45a7-870f-7e135c8bd5ca
ms.date: 05/02/2018
ms.keywords: "*PNDIS_SWITCH_PORT_PROPERTY_CUSTOM, NDIS_SWITCH_PORT_PROPERTY_CUSTOM, NDIS_SWITCH_PORT_PROPERTY_CUSTOM structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_PORT_PROPERTY_CUSTOM, PNDIS_SWITCH_PORT_PROPERTY_CUSTOM structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PORT_PROPERTY_CUSTOM, netvista.ndis_switch_port_property_custom, ntddndis/NDIS_SWITCH_PORT_PROPERTY_CUSTOM, ntddndis/PNDIS_SWITCH_PORT_PROPERTY_CUSTOM"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddndis.h
api_name:
- NDIS_SWITCH_PORT_PROPERTY_CUSTOM
product:
- Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_PROPERTY_CUSTOM, *PNDIS_SWITCH_PORT_PROPERTY_CUSTOM
---

# _NDIS_SWITCH_PORT_PROPERTY_CUSTOM structure


## -description



The <b>NDIS_SWITCH_PORT_PROPERTY_CUSTOM</b> structure specifies a custom policy property for a Hyper-V extensible switch port. 

Independent software vendors (ISVs) define the format for the custom properties. The format of the custom property is proprietary to the ISV.




## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PORT_PROPERTY_CUSTOM</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PORT_PROPERTY_CUSTOM</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value:  





#### NDIS_SWITCH_PORT_PROPERTY_CUSTOM_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_PORT_PROPERTY_CUSTOM_REVISION_1.


### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


### -field PropertyBufferLength

A ULONG value that specifies the size, in bytes, of the buffer that contains the custom port property.


### -field PropertyBufferOffset

A ULONG value that specifies the offset, in bytes, to the property buffer. The offset is measured from the start of the <b>NDIS_SWITCH_PORT_PROPERTY_CUSTOM</b> structure up to the beginning of the property buffer.


## -remarks



The <b>NDIS_SWITCH_PORT_PROPERTY_CUSTOM</b> structure is used in the following OID set requests: 

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-property-add">OID_SWITCH_PORT_PROPERTY_ADD</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-property-update">OID_SWITCH_PORT_PROPERTY_UPDATE</a>


</li>
</ul>
The <b>NDIS_SWITCH_PORT_PROPERTY_CUSTOM</b> structure follows the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_switch_port_property_parameters">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a> structure in the buffer that is associated with these OID set requests. The <b>InformationBuffer</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure contains a pointer to this buffer.

Extensible switch extensions can access the custom port property buffer inside an <b>NDIS_SWITCH_PORT_PROPERTY_CUSTOM</b> structure by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-switch-port-property-custom-get-buffer">NDIS_SWITCH_PORT_PROPERTY_CUSTOM_GET_BUFFER</a> macro.

For more information about extensible switch policies, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/hyper-v-extensible-switch-policies">Hyper-V Extensible Switch Policies</a>.




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-switch-port-property-custom-get-buffer">NDIS_SWITCH_PORT_PROPERTY_CUSTOM_GET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_switch_port_property_parameters">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-property-add">OID_SWITCH_PORT_PROPERTY_ADD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-property-update">OID_SWITCH_PORT_PROPERTY_UPDATE</a>
 

 

