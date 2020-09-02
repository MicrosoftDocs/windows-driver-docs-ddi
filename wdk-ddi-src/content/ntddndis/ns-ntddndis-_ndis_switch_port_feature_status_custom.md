---
UID: NS:ntddndis._NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM
title: _NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM (ntddndis.h)
description: The NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM structure specifies the custom status information for a Hyper-V extensible switch port.
old-location: netvista\ndis_switch_port_feature_status_custom.htm
tech.root: netvista
ms.assetid: B3655B3C-4E9E-4FAC-9AAB-B7D4BFB2B91E
ms.date: 05/02/2018
keywords: ["NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM structure"]
ms.keywords: "*PNDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM, NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM, NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM, PNDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM, netvista.ndis_switch_port_feature_status_custom, ntddndis/NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM, ntddndis/PNDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM"
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
req.typenames: NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM, *PNDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM
f1_keywords:
 - _NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM
 - ntddndis/_NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM
 - PNDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM
 - ntddndis/PNDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM
 - NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM
 - ntddndis/NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM
---

# _NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM structure


## -description

The <b>NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM</b> structure specifies the  custom status information for a Hyper-V extensible switch port. This information is known as <i>feature status</i> information. The format of this information is defined by the independent software vendor (ISV).

## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 





#### NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM_REVISION_1.

### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.

### -field FeatureStatusBufferLength

A ULONG value that specifies the size, in bytes, of the feature status buffer.

### -field FeatureStatusBufferOffset

A ULONG value that specifies the offset, in bytes, to the feature status buffer that follows the <b>NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM</b> structure. The offset is measured from the start of the <b>NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM</b> structure up to the beginning of the feature status buffer.

## -remarks

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_feature_status_parameters">NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</a> structure is used in OID method requests of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-feature-status-query">OID_SWITCH_PORT_FEATURE_STATUS_QUERY</a>. This OID request returns the following structures in the information buffer that is associated with the OID request:<ul>
<li>
An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_feature_status_parameters">NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</a> structure that specifies the parameters for the feature status information that is to be returned for an extensible switch port.  The switch extension populates the <b>FeatureStatusVersion</b> member of the structure to reflect the version of the custom status being returned in the NDIS_SWITCH_FEATURE_STATUS_CUSTOM buffer. The Hyper-v Extensible switch populates all other members when issuing the query OID.

</li>
<li>
An <b>NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM</b> structure that contains the feature status data for the specified extensible switch port.  The switch extension populates the <b>FeatureStatusCustomBufferLength</b> member of the structure to reflect the size of the custom status being returned. The Hyper-v Extensible switch populates all other members when issuing the query OID.

</li>
</ul> The <b>InformationBuffer</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure contains a pointer to this information buffer.

## -see-also

<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_feature_status_parameters">NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-feature-status-query">OID_SWITCH_PORT_FEATURE_STATUS_QUERY</a>

