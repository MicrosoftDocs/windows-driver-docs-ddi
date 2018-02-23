---
UID: NS:ntddndis._NDIS_SWITCH_PROPERTY_PARAMETERS
title: "_NDIS_SWITCH_PROPERTY_PARAMETERS"
author: windows-driver-content
description: The NDIS_SWITCH_PROPERTY_PARAMETERS structure specifies the parameters for a policy property of a Hyper-V extensible switch.
old-location: netvista\ndis_switch_property_parameters.htm
old-project: netvista
ms.assetid: c5a8f551-36a5-4d49-b521-4ac43ea2fff8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "_NDIS_SWITCH_PROPERTY_PARAMETERS, ntddndis/PNDIS_SWITCH_PROPERTY_PARAMETERS, *PNDIS_SWITCH_PROPERTY_PARAMETERS, ntddndis/NDIS_SWITCH_PROPERTY_PARAMETERS, netvista.ndis_switch_property_parameters, PNDIS_SWITCH_PROPERTY_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_PROPERTY_PARAMETERS, NDIS_SWITCH_PROPERTY_PARAMETERS structure [Network Drivers Starting with Windows Vista], NDIS_SWITCH_PROPERTY_PARAMETERS"
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
-	NDIS_SWITCH_PROPERTY_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PROPERTY_PARAMETERS, *PNDIS_SWITCH_PROPERTY_PARAMETERS
---

# _NDIS_SWITCH_PROPERTY_PARAMETERS structure


## -description


The <b>NDIS_SWITCH_PROPERTY_PARAMETERS</b> structure specifies the parameters for a policy property of a Hyper-V extensible switch. 


## -syntax


````
typedef struct _NDIS_SWITCH_PROPERTY_PARAMETERS {
  NDIS_OBJECT_HEADER                       Header;
  ULONG                                    Flags;
  NDIS_SWITCH_PROPERTY_TYPE                PropertyType;
  NDIS_SWITCH_OBJECT_ID                    PropertyId;
  NDIS_SWITCH_OBJECT_VERSION               PropertyVersion;
  NDIS_SWITCH_OBJECT_SERIALIZATION_VERSION SerializationVersion;
  NDIS_SWITCH_OBJECT_INSTANCE_ID           PropertyInstanceId;
  ULONG                                    PropertyBufferLength;
  ULONG                                    PropertyBufferOffset;
} NDIS_SWITCH_PROPERTY_PARAMETERS, *PNDIS_SWITCH_PROPERTY_PARAMETERS;
````


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PROPERTY_PARAMETERS</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PROPERTY_PARAMETERS</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value:





#### NDIS_SWITCH_PROPERTY_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_PROPERTY_PARAMETERS_REVISION_1.


### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


### -field PropertyType

 An <a href="..\ntddndis\ne-ntddndis-_ndis_switch_property_type.md">NDIS_SWITCH_PROPERTY_TYPE</a> enumeration value that specifies the type of extensible switch property that is contained within the property buffer.


### -field PropertyId

A GUID value that identifies the extensible switch property.

For more information, see the Remarks section.

<div class="alert"><b>Note</b>  The extensible switch extension must ignore this member unless the <b>PropertyType</b> member is set to <b>NdisSwitchPropertyTypeCustom</b>.</div>
<div> </div>

### -field PropertyVersion

An NDIS_SWITCH_OBJECT_VERSION value that identifies the version of the extensible switch property.




### -field SerializationVersion

An NDIS_SWITCH_OBJECT_SERIALIZATION_VERSION value that identifies the format version of the serialized extensible switch property data. This data is serialized for access by the extension from the Managed Object Format (MOF) file that defined the property.

<div class="alert"><b>Note</b>  For Windows Server 2012, the <b>SerializationVersion</b> member must be set to NDIS_SWITCH_OBJECT_SERIALIZATION_VERSION_1.</div>
<div> </div>

### -field PropertyInstanceId

An NDIS_SWITCH_OBJECT_INSTANCE_ID value that specifies the instance identifier of the  extensible switch property.




### -field PropertyBufferLength

A ULONG value that specifies the size, in bytes, of the property buffer.


### -field PropertyBufferOffset

A ULONG value that specifies the offset, in bytes, to the property buffer that follows the <b>NDIS_SWITCH_PROPERTY_PARAMETERS</b> structure. The offset is measured from the start of the <b>NDIS_SWITCH_PROPERTY_PARAMETERS</b> structure up to the beginning of the property buffer. 


## -remarks



The <b>NDIS_SWITCH_PROPERTY_PARAMETERS</b> structure is used in the following OID set requests:

<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598280">OID_SWITCH_PROPERTY_ADD</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598283">OID_SWITCH_PROPERTY_UPDATE</a>


</li>
</ul>
The property buffer contains a structure that is associated with the <b>PropertyType</b> member. The property buffer follows the <b>NDIS_SWITCH_PROPERTY_PARAMETERS</b> structure in the information buffer that is associated with these OID set requests. The <b>InformationBuffer</b> member of the <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure contains a pointer to this information buffer.

<div class="alert"><b>Note</b>  Starting with Windows Server 2012, the <b>PropertyType</b> member must be set to <b>NdisSwitchPropertyTypeCustom</b> and the property buffer must contain an <a href="..\ntddndis\ns-ntddndis-_ndis_switch_property_custom.md">NDIS_SWITCH_PROPERTY_CUSTOM</a> structure.</div>
<div> </div>
Extensible switch extensions can access the  extensible switch property buffer inside an <b>NDIS_SWITCH_PROPERTY_PARAMETERS</b> structure by using the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598256">NDIS_SWITCH_PROPERTY_PARAMETERS_GET_PROPERTY</a> macro.

For more information about extensible switch policies, see <a href="https://msdn.microsoft.com/8AB85E48-EF37-4D42-873B-34D4835AF22E">Hyper-V Extensible Switch Policies</a>.




## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598280">OID_SWITCH_PROPERTY_ADD</a>



<a href="..\ntddndis\ne-ntddndis-_ndis_switch_property_type.md">NDIS_SWITCH_PROPERTY_TYPE</a>



<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598283">OID_SWITCH_PROPERTY_UPDATE</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_switch_property_custom.md">NDIS_SWITCH_PROPERTY_CUSTOM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598256">NDIS_SWITCH_PROPERTY_PARAMETERS_GET_PROPERTY</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PROPERTY_PARAMETERS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

