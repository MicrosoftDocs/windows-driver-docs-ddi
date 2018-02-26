---
UID: NS:ks.KSPROPERTY_MEMBERSLIST
title: KSPROPERTY_MEMBERSLIST
author: windows-driver-content
description: The KSPROPERTY_MEMBERSLIST structure contains a list of legal values or ranges for a property.
old-location: stream\ksproperty_memberslist.htm
old-project: stream
ms.assetid: 2354da98-8663-4758-add7-3ac4350f563c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , *, *PKSPROPERTY_MEMBERSLIST, ,, B, E, I, K, KSPROPERTY_MEMBERSLIST, KSPROPERTY_MEMBERSLIST structure [Streaming Media Devices], L, M, O, P, PKSPROPERTY_MEMBERSLIST, PKSPROPERTY_MEMBERSLIST structure pointer [Streaming Media Devices], R, S, T, Y, _, ks-struct_44a818f7-bffd-4aa5-aa30-b6376c0593ca.xml, ks/KSPROPERTY_MEMBERSLIST, ks/PKSPROPERTY_MEMBERSLIST, stream.ksproperty_memberslist"
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
-	KSPROPERTY_MEMBERSLIST
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_MEMBERSLIST, *PKSPROPERTY_MEMBERSLIST
---

# KSPROPERTY_MEMBERSLIST structure


## -description


The KSPROPERTY_MEMBERSLIST structure contains a list of legal values or ranges for a property.


## -syntax


````
typedef struct {
  KSPROPERTY_MEMBERSHEADER MembersHeader;
  const VOID               *Members;
} KSPROPERTY_MEMBERSLIST, *PKSPROPERTY_MEMBERSLIST;
````


## -struct-fields




### -field MembersHeader

Indicates a structure of type <a href="..\ks\ns-ks-ksproperty_membersheader.md">KSPROPERTY_MEMBERSHEADER</a> that specifies the size and type of information contained in the <b>Members</b> array.


### -field Members

Points to an array of entries that specify legal values or ranges for a property. Each entry describes a value or a set of a values.


## -remarks



The type of structures pointed to in the <b>Members</b> array depends on the value of <b>MembersHeader.MembersFlags</b>. See <a href="..\ks\ns-ks-ksproperty_membersheader.md">KSPROPERTY_MEMBERSHEADER</a> for details on possible flag values.  

The <a href="..\ks\ns-ks-ksproperty_values.md">KSPROPERTY_VALUES</a> structure contains a pointer to an array of KSPROPERTY_MEMBERSLIST structures that specify valid range and value information for a property. In turn, a <a href="..\ks\ns-ks-ksproperty_item.md">KSPROPERTY_ITEM</a> structure contains a pointer to a KSPROPERTY_VALUES structure.

For more information, see <a href="https://msdn.microsoft.com/a385929e-1934-4d88-aaf9-ff1ddbfd30f7">KS Properties</a>.




## -see-also

<a href="..\ks\ns-ks-ksproperty_description.md">KSPROPERTY_DESCRIPTION</a>



<a href="..\ks\ns-ks-ksproperty_membersheader.md">KSPROPERTY_MEMBERSHEADER</a>



<a href="..\ks\ns-ks-ksproperty_stepping_longlong.md">KSPROPERTY_STEPPING_LONGLONG</a>



<a href="..\ks\ns-ks-ksproperty_values.md">KSPROPERTY_VALUES</a>



<a href="..\ks\ns-ks-ksproperty_stepping_long.md">KSPROPERTY_STEPPING_LONG</a>



<a href="..\ks\ns-ks-ksproperty_item.md">KSPROPERTY_ITEM</a>



<a href="..\ks\ns-ks-ksproperty_bounds_long.md">KSPROPERTY_BOUNDS_LONG</a>



<a href="..\ks\ns-ks-ksproperty_bounds_longlong.md">KSPROPERTY_BOUNDS_LONGLONG</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_MEMBERSLIST structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

