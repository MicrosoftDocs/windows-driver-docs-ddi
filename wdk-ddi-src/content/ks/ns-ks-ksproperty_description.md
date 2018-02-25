---
UID: NS:ks.KSPROPERTY_DESCRIPTION
title: KSPROPERTY_DESCRIPTION
author: windows-driver-content
description: The KSPROPERTY_DESCRIPTION structure specifies the size and type of values contained in a specific property.
old-location: stream\ksproperty_description.htm
old-project: stream
ms.assetid: d3d59dca-7214-493c-bb70-4391696fe017
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PKSPROPERTY_DESCRIPTION, ,, C, D, E, I, K, KSPROPERTY_DESCRIPTION, KSPROPERTY_DESCRIPTION structure [Streaming Media Devices], N, O, P, PKSPROPERTY_DESCRIPTION, PKSPROPERTY_DESCRIPTION structure pointer [Streaming Media Devices], R, S, T, Y, _, ks-struct_37ee8090-f90e-40a9-8731-3521d1d3a157.xml, ks/KSPROPERTY_DESCRIPTION, ks/PKSPROPERTY_DESCRIPTION, stream.ksproperty_description"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KSPROPERTY_DESCRIPTION
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_DESCRIPTION, *PKSPROPERTY_DESCRIPTION
---

# KSPROPERTY_DESCRIPTION structure


## -description


The KSPROPERTY_DESCRIPTION structure specifies the size and type of values contained in a specific property.


## -syntax


````
typedef struct {
  ULONG        AccessFlags;
  ULONG        DescriptionSize;
  KSIDENTIFIER PropTypeSet;
  ULONG        MembersListCount;
  ULONG        Reserved;
} KSPROPERTY_DESCRIPTION, *PKSPROPERTY_DESCRIPTION;
````


## -struct-fields




### -field AccessFlags

Specifies the access allowed to this property. A basic-support request sets this member to the bitwise OR of the flags for all the access types that the handler supports for this property. For a list of possible flag values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>.


### -field DescriptionSize

Specifies total size in bytes of the KSPROPERTY_DESCRIPTION structure and any values entries that follow it. If the basic-support property request returns no values entries, this member is the size of KSPROPERTY_DESCRIPTION.


### -field PropTypeSet

A structure of type <a href="..\ks\ns-ks-ksidentifier.md">KSIDENTIFIER</a>. If supported by the specific property, specifies the type of values contained in this property. This group is uniquely specified by a GUID, such that new types of values may be created without overlapping with extensions to this set. The value types indicate the type of the value (like VT_BOOL, VT_UI4 in the standard set). This is GUID_NULL, with an identifier of zero, if values information is not supported by this property.


### -field MembersListCount

Specifies the number of <a href="..\ks\ns-ks-ksproperty_membersheader.md">KSPROPERTY_MEMBERSHEADER</a> structures to follow this header.


### -field Reserved

Reserved for future use. Set to zero.


## -remarks



A driver returns the <b>KSPROPERTY_DESCRIPTION</b> structure in response to a basic support property request from a client.

The property values type set is specified by a KSIDENTIFIER structure. The basic set supported is <a href="https://msdn.microsoft.com/library/windows/hardware/ff566576">KSPROPSETID_General</a>. The identifiers within that set are the standard VARENUM types used for OLE.

The values information that may follow the KSPROPERTY_DESCRIPTION structure is described by a list of <a href="..\ks\ns-ks-ksproperty_memberslist.md">KSPROPERTY_MEMBERSLIST</a> structures, each of which contains data range information.

For more information, see <a href="https://msdn.microsoft.com/a385929e-1934-4d88-aaf9-ff1ddbfd30f7">KS Properties</a>.




## -see-also

<a href="..\ks\ns-ks-ksproperty_values.md">KSPROPERTY_VALUES</a>



<a href="..\ks\ns-ks-ksproperty_membersheader.md">KSPROPERTY_MEMBERSHEADER</a>



<a href="..\ks\ns-ks-ksidentifier.md">KSIDENTIFIER</a>



<a href="..\ks\ns-ks-ksproperty_item.md">KSPROPERTY_ITEM</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_DESCRIPTION structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

