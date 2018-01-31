---
UID: NS:ntddndis._NDIS_SWITCH_PROPERTY_CUSTOM
title: "_NDIS_SWITCH_PROPERTY_CUSTOM"
author: windows-driver-content
description: The NDIS_SWITCH_PROPERTY_CUSTOM structure specifies a custom profile property for the Hyper-V extensible switch. Independent software vendors (ISVs) define the format for the custom properties. The format of the custom property is proprietary to the ISV.
old-location: netvista\ndis_switch_property_custom.htm
old-project: netvista
ms.assetid: 9ded1ec7-1ca2-4410-8ede-b2ccc33571b1
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndis_switch_property_custom, NDIS_SWITCH_PROPERTY_CUSTOM, PNDIS_SWITCH_PROPERTY_CUSTOM structure pointer [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_PROPERTY_CUSTOM, _NDIS_SWITCH_PROPERTY_CUSTOM, ntddndis/PNDIS_SWITCH_PROPERTY_CUSTOM, *PNDIS_SWITCH_PROPERTY_CUSTOM, NDIS_SWITCH_PROPERTY_CUSTOM structure [Network Drivers Starting with Windows Vista], ntddndis/NDIS_SWITCH_PROPERTY_CUSTOM
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
-	NDIS_SWITCH_PROPERTY_CUSTOM
product: Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PROPERTY_CUSTOM, *PNDIS_SWITCH_PROPERTY_CUSTOM
---

# _NDIS_SWITCH_PROPERTY_CUSTOM structure


## -description



The <b>NDIS_SWITCH_PROPERTY_CUSTOM</b> structure specifies a custom profile property for the Hyper-V extensible switch. 

Independent software vendors (ISVs) define the format for the custom properties. The format of the custom property is proprietary to the ISV.




## -syntax


````
typedef struct _NDIS_SWITCH_PROPERTY_CUSTOM {
  NDIS_OBJECT_HEADER Header;
  ULONG              Flags;
  ULONG              PropertyBufferLength;
  ULONG              PropertyBufferOffset;
} NDIS_SWITCH_PROPERTY_CUSTOM, *PNDIS_SWITCH_PROPERTY_CUSTOM;
````


## -struct-fields




#### - Header

The type, revision, and size of the <b>NDIS_SWITCH_PROPERTY_CUSTOM</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PROPERTY_CUSTOM</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value:




#### NDIS_SWITCH_PROPERTY_CUSTOM_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_PROPERTY_CUSTOM_REVISION_1.


#### - Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


#### - PropertyBufferLength

A ULONG value that specifies the size, in bytes, of the buffer that contains the custom extensible switch property.


#### - PropertyBufferOffset

A ULONG value that specifies the offset, in bytes, to the property buffer. The offset is measured from the start of the <b>NDIS_SWITCH_PROPERTY_CUSTOM</b> structure up to the beginning of the property buffer.


## -remarks


The <b>NDIS_SWITCH_PROPERTY_CUSTOM</b> structure is used in the following OID set requests: 
<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598280">OID_SWITCH_PROPERTY_ADD</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598283">OID_SWITCH_PROPERTY_UPDATE</a>


</li>
</ul>The <b>NDIS_SWITCH_PROPERTY_CUSTOM</b> structure follows the <a href="..\ntddndis\ns-ntddndis-_ndis_switch_property_parameters.md">NDIS_SWITCH_PROPERTY_PARAMETERS</a> structure in the buffer that is associated with these OID set requests. The <b>InformationBuffer</b> member of the <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure contains a pointer to this buffer.

Extensible switch extensions can access the custom extensible switch property buffer that is specified by an <b>NDIS_SWITCH_PROPERTY_CUSTOM</b> structure  by using the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598248">NDIS_SWITCH_PROPERTY_CUSTOM_GET_BUFFER</a> macro.

For more information about extensible switch policies, see <a href="https://msdn.microsoft.com/8AB85E48-EF37-4D42-873B-34D4835AF22E">Hyper-V Extensible Switch Policies</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598248">NDIS_SWITCH_PROPERTY_CUSTOM_GET_BUFFER</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598283">OID_SWITCH_PROPERTY_UPDATE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598280">OID_SWITCH_PROPERTY_ADD</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_switch_property_parameters.md">NDIS_SWITCH_PROPERTY_PARAMETERS</a>

<b></b>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PROPERTY_CUSTOM structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

