---
UID: NS:ntddndis._NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM
title: _NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM
author: windows-driver-content
description: The NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM structure specifies the custom status information for a Hyper-V extensible switch port.
old-location: netvista\ndis_switch_port_feature_status_custom.htm
old-project: netvista
ms.assetid: B3655B3C-4E9E-4FAC-9AAB-B7D4BFB2B91E
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM, NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM, *PNDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM
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
req.alt-api: NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM
req.alt-loc: Ntddndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM, *PNDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM
---

# _NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM structure



## -description
The <b>NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM</b> structure specifies the  custom status information for a Hyper-V extensible switch port. This information is known as <i>feature status</i> information. The format of this information is defined by the independent software vendor (ISV). 



## -syntax

````
typedef struct _NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM {
  NDIS_OBJECT_HEADER Header;
  ULONG              Flags;
  ULONG              FeatureStatusBufferLength;
  ULONG              FeatureStatusBufferOffset;
} NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM, *PNDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM;
````


## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 




### -field NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM_REVISION_1.

</dd>
</dl>

### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


### -field FeatureStatusBufferLength

A ULONG value that specifies the size, in bytes, of the feature status buffer.


### -field FeatureStatusBufferOffset

A ULONG value that specifies the offset, in bytes, to the feature status buffer that follows the <b>NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM</b> structure. The offset is measured from the start of the <b>NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM</b> structure up to the beginning of the feature status buffer. 


## -remarks
The <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_feature_status_parameters.md">NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</a> structure is used in OID method requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598274">OID_SWITCH_PORT_FEATURE_STATUS_QUERY</a>. This OID request returns the following structures in the information buffer that is associated with the OID request:<ul>
<li>
An <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_feature_status_parameters.md">NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</a> structure that specifies the parameters for the feature status information that is to be returned for an extensible switch port.  The switch extension populates the <b>FeatureStatusVersion</b> member of the structure to reflect the version of the custom status being returned in the NDIS_SWITCH_FEATURE_STATUS_CUSTOM buffer. The Hyper-v Extensible switch populates all other members when issuing the query OID.

</li>
<li>
An <b>NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM</b> structure that contains the feature status data for the specified extensible switch port.  The switch extension populates the <b>FeatureStatusCustomBufferLength</b> member of the structure to reflect the size of the custom status being returned. The Hyper-v Extensible switch populates all other members when issuing the query OID.

</li>
</ul> The <b>InformationBuffer</b> member of the <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure contains a pointer to this information buffer.

An <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_feature_status_parameters.md">NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</a> structure that specifies the parameters for the feature status information that is to be returned for an extensible switch port.  The switch extension populates the <b>FeatureStatusVersion</b> member of the structure to reflect the version of the custom status being returned in the NDIS_SWITCH_FEATURE_STATUS_CUSTOM buffer. The Hyper-v Extensible switch populates all other members when issuing the query OID.

An <b>NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM</b> structure that contains the feature status data for the specified extensible switch port.  The switch extension populates the <b>FeatureStatusCustomBufferLength</b> member of the structure to reflect the size of the custom status being returned. The Hyper-v Extensible switch populates all other members when issuing the query OID.


## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_feature_status_parameters.md">NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598274">OID_SWITCH_PORT_FEATURE_STATUS_QUERY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

