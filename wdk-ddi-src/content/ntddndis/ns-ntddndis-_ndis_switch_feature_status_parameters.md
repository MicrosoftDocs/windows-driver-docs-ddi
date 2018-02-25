---
UID: NS:ntddndis._NDIS_SWITCH_FEATURE_STATUS_PARAMETERS
title: "_NDIS_SWITCH_FEATURE_STATUS_PARAMETERS"
author: windows-driver-content
description: The NDIS_SWITCH_FEATURE_STATUS_PARAMETERS structure specifies the parameters for the custom status information of a Hyper-V extensible switch.
old-location: netvista\ndis_switch_feature_status_parameters.htm
old-project: netvista
ms.assetid: 6d365e49-49ff-4b00-8cce-cf0c25cc2491
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PNDIS_SWITCH_FEATURE_STATUS_PARAMETERS, ,, A, C, D, E, F, H, I, M, N, NDIS_SWITCH_FEATURE_STATUS_PARAMETERS, NDIS_SWITCH_FEATURE_STATUS_PARAMETERS structure [Network Drivers Starting with Windows Vista], P, PNDIS_SWITCH_FEATURE_STATUS_PARAMETERS, PNDIS_SWITCH_FEATURE_STATUS_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], R, S, T, U, W, _, _NDIS_SWITCH_FEATURE_STATUS_PARAMETERS, netvista.ndis_switch_feature_status_parameters, ntddndis/NDIS_SWITCH_FEATURE_STATUS_PARAMETERS, ntddndis/PNDIS_SWITCH_FEATURE_STATUS_PARAMETERS"
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddndis.h
apiname:
-	NDIS_SWITCH_FEATURE_STATUS_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_SWITCH_FEATURE_STATUS_PARAMETERS, *PNDIS_SWITCH_FEATURE_STATUS_PARAMETERS
---

# _NDIS_SWITCH_FEATURE_STATUS_PARAMETERS structure


## -description



The <b>NDIS_SWITCH_FEATURE_STATUS_PARAMETERS</b> structure specifies the parameters for the custom status information of a Hyper-V extensible switch. This information is known as <i>feature status</i> information. The format of this information is defined by the independent software vendor (ISV). 

The status information is specified through an <a href="..\ntddndis\ns-ntddndis-_ndis_switch_feature_status_custom.md">NDIS_SWITCH_FEATURE_STATUS_CUSTOM</a> structure that is returned through an object identifier (OID) method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598260">OID_SWITCH_FEATURE_STATUS_QUERY</a>.




## -syntax


````
typedef struct _NDIS_SWITCH_FEATURE_STATUS_PARAMETERS {
  NDIS_OBJECT_HEADER                       Header;
  ULONG                                    Flags;
  NDIS_SWITCH_FEATURE_STATUS_TYPE          FeatureStatusType;
  NDIS_SWITCH_OBJECT_ID                    FeatureStatusId;
  NDIS_SWITCH_OBJECT_INSTANCE_ID           FeatureStatusInstanceId;
  NDIS_SWITCH_OBJECT_VERSION               FeatureStatusVersion;
  NDIS_SWITCH_OBJECT_SERIALIZATION_VERSION SerializationVersion;
  ULONG                                    FeatureStatusBufferOffset;
  ULONG                                    FeatureStatusBufferLength;
} NDIS_SWITCH_FEATURE_STATUS_PARAMETERS, *PNDIS_SWITCH_FEATURE_STATUS_PARAMETERS;
````


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_FEATURE_STATUS_PARAMETERS</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_FEATURE_STATUS_PARAMETERS</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 





#### NDIS_SWITCH_FEATURE_STATUS_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_FEATURE_STATUS_PARAMETERS_REVISION_1.


### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


### -field FeatureStatusType

An <a href="..\ntddndis\ne-ntddndis-_ndis_switch_feature_status_type.md">NDIS_SWITCH_FEATURE_STATUS_TYPE</a> enumeration value that specifies the type of the feature status information for the extensible switch.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, this member must be set to <b>NdisSwitchFeatureStatusTypeCustom</b>.</div>
<div> </div>

### -field FeatureStatusId

A GUID value that identifies the feature status information for the extensible switch.

This  value is defined in the managed object format (MOF) class definition for the feature status information. For more information, see <a href="https://msdn.microsoft.com/DB80E86D-8553-47B5-8AE1-6D430FDDE206">Custom Switch Property Definition and Registration</a>.


### -field FeatureStatusInstanceId

An NDIS_SWITCH_OBJECT_INSTANCE_ID value that identifies the instance of the  feature status information for the extensible switch.




### -field FeatureStatusVersion

An NDIS_SWITCH_OBJECT_VERSION value that identifies the version of the feature status information for the extensible switch. This value is defined in the MOF class definition for the feature status information.


### -field SerializationVersion

An NDIS_SWITCH_OBJECT_SERIALIZATION_VERSION value that identifies the format version of the serialized status information for the feature status information. This data is serialized for access by the extension from the MOF file that defined the property.

<div class="alert"><b>Note</b>  For Windows Server 2012, the <b>SerializationVersion</b> member must be set to NDIS_SWITCH_OBJECT_SERIALIZATION_VERSION_1.</div>
<div> </div>

### -field FeatureStatusBufferOffset

A ULONG value that specifies the offset, in bytes, to the feature status buffer  that follows the <b>NDIS_SWITCH_FEATURE_STATUS_PARAMETERS</b> structure. The status buffer contains an <a href="..\ntddndis\ns-ntddndis-_ndis_switch_feature_status_custom.md">NDIS_SWITCH_FEATURE_STATUS_CUSTOM</a> structure. 

The offset is measured from the start of the <b>NDIS_SWITCH_FEATURE_STATUS_PARAMETERS</b> structure up to the beginning of the <a href="..\ntddndis\ns-ntddndis-_ndis_switch_feature_status_custom.md">NDIS_SWITCH_FEATURE_STATUS_CUSTOM</a> structure. 


### -field FeatureStatusBufferLength

A ULONG value that specifies the size, in bytes, of the feature status buffer.


## -remarks



The <b>NDIS_SWITCH_FEATURE_STATUS_PARAMETERS</b> structure is used in OID method requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598260">OID_SWITCH_FEATURE_STATUS_QUERY</a>. This OID request returns the following structures in the information buffer that is associated with the OID request: 

<ul>
<li>
An <b>NDIS_SWITCH_FEATURE_STATUS_PARAMETERS</b> structure that specifies the status parameters for the feature status information of the extensible switch. The switch extension populates the <b>FeatureStatusVersion</b> member of the structure to reflect the version of the custom status being returned in the NDIS_SWITCH_FEATURE_STATUS_CUSTOM buffer. The Hyper-v Extensible switch populates all other members when issuing the query OID.

</li>
<li>
An <a href="..\ntddndis\ns-ntddndis-_ndis_switch_feature_status_custom.md">NDIS_SWITCH_FEATURE_STATUS_CUSTOM</a> structure that contains the feature status information for the extensible switch.  The switch extension populates the <b>FeatureStatusCustomBufferLength</b> member of the structure to reflect the size of the custom status being returned. The Hyper-v Extensible switch populates all other members when issuing the query OID.

</li>
</ul>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598260">OID_SWITCH_FEATURE_STATUS_QUERY</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_switch_feature_status_custom.md">NDIS_SWITCH_FEATURE_STATUS_CUSTOM</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ntddndis\ne-ntddndis-_ndis_switch_feature_status_type.md">NDIS_SWITCH_FEATURE_STATUS_TYPE</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_FEATURE_STATUS_PARAMETERS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

