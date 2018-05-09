---
UID: NS:ks.KSPROPERTY_VALUES
title: KSPROPERTY_VALUES
author: windows-driver-content
description: The KSPROPERTY_VALUES structure describes the type and acceptable default values of a property.
old-location: stream\ksproperty_values.htm
old-project: stream
ms.assetid: 0837f458-6585-4ac9-a166-e72f715238a1
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PKSPROPERTY_VALUES, KSPROPERTY_VALUES, KSPROPERTY_VALUES structure [Streaming Media Devices], PKSPROPERTY_VALUES, PKSPROPERTY_VALUES structure pointer [Streaming Media Devices], ks-struct_a9156948-e21f-41d4-bb63-9c85fdbf57f3.xml, ks/KSPROPERTY_VALUES, ks/PKSPROPERTY_VALUES, stream.ksproperty_values"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSPROPERTY_VALUES
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_VALUES, *PKSPROPERTY_VALUES
---

# KSPROPERTY_VALUES structure


## -description


The KSPROPERTY_VALUES structure describes the type and acceptable default values of a property.


## -struct-fields




### -field PropTypeSet

Specifies a KSIDENTIFIER structure (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561744">KSEVENT</a>) that identifies the data type of the property. The <b>Set</b> member of a KSIDENTIFIER structure indicates the set of value types supported, and the <b>Id</b> member of the same structure identifies the type within the set.


### -field MembersListCount

Specifies the number of entries in the array pointed to by <b>MembersList</b>.


### -field MembersList

Points to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff565190">KSPROPERTY_MEMBERSLIST</a> structures. Each entry specifies a list of possible values or sets of values that the property may assume.


## -remarks



<b>PropTypeSet.Set</b> almost always equals KSPROPTYPESETID_General. The individual value types in KSPROPTYPESETID_General correspond to the VARENUM types documented in the Microsoft Windows SDK.

Possible values for PropTypeSet.Id include:

<table>
<tr>
<th>Value</th>
<th>Data type</th>
</tr>
<tr>
<td>
VT_I4

</td>
<td>
Signed 4-byte quantity

</td>
</tr>
<tr>
<td>
VT_UI4

</td>
<td>
Unsigned 4-byte quantity

</td>
</tr>
</table>
 

A driver can specify a pointer to a KSPROPERTY_VALUES structure in the relevant KSPROPERTY_ITEM for a property.

For more information, see <a href="https://msdn.microsoft.com/a385929e-1934-4d88-aaf9-ff1ddbfd30f7">KS Properties</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561744">KSEVENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565132">KSPROPERTY_DESCRIPTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565176">KSPROPERTY_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565190">KSPROPERTY_MEMBERSLIST</a>
 

 

