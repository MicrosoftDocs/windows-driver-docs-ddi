---
UID: NS:ks.KSPROPERTY_MEMBERSHEADER
title: KSPROPERTY_MEMBERSHEADER
author: windows-driver-content
description: A driver provides a structure of type KSPROPERTY_MEMBERSHEADER to describe the size and type of each element in an array containing property values or ranges.
old-location: stream\ksproperty_membersheader.htm
tech.root: stream
ms.assetid: 8a5d8f8c-4924-4ae0-a7b2-8d2b04a49a9e
ms.date: 4/23/2018
ms.keywords: "*PKSPROPERTY_MEMBERSHEADER, KSPROPERTY_MEMBERSHEADER, KSPROPERTY_MEMBERSHEADER structure [Streaming Media Devices], PKSPROPERTY_MEMBERSHEADER, PKSPROPERTY_MEMBERSHEADER structure pointer [Streaming Media Devices], ks-struct_d43fb5ec-043b-4378-8bdb-aaf80a616150.xml, ks/KSPROPERTY_MEMBERSHEADER, ks/PKSPROPERTY_MEMBERSHEADER, stream.ksproperty_membersheader"
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
-	KSPROPERTY_MEMBERSHEADER
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_MEMBERSHEADER, *PKSPROPERTY_MEMBERSHEADER
---

# KSPROPERTY_MEMBERSHEADER structure


## -description


A driver provides a structure of type KSPROPERTY_MEMBERSHEADER to describe the size and type of each element in an array containing property values or ranges.


## -struct-fields




### -field MembersFlags

Specifies the type of entries in the members list. The size of valid values is determined by value type, as specified in the <b>PropTypeSet</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565132">KSPROPERTY_DESCRIPTION</a> structure. The number of range pairs is determined by <b>MembersCount</b>. This should be one of the values listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
KSPROPERTY_MEMBER_RANGES

</td>
<td>
Indicates that list members are ranges, of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff564394">KSPROPERTY_BOUNDS_LONG</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff564395">KSPROPERTY_BOUNDS_LONGLONG</a>.

</td>
</tr>
<tr>
<td>

<dl>
<dt>KSPROPERTY_MEMBER</dt>
<dt>_STEPPEDRANGES</dt>
</dl>


</td>
<td>
Indicates that the following members are stepped values within ranges, of type <a href="https://msdn.microsoft.com/library/windows/hardware/dn936838">KSPROPERTY_STEPPING_LONG</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/dn936841">KSPROPERTY_STEPPING_LONGLONG</a>..

</td>
</tr>
<tr>
<td>
KSPROPERTY_MEMBER_VALUES

</td>
<td>
Each entry in the members array is a single value.

</td>
</tr>
</table>
 


### -field MembersSize

Specifies the size, in bytes, of an individual array element.


### -field MembersCount

Specifies the number of entries in the members array.


### -field Flags

Specifies the type of entries in the members list. The size of valid values is determined by value type, as specified in the <b>PropTypeSet</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565132">KSPROPERTY_DESCRIPTION</a> structure. The number of range pairs is determined by <b>MembersCount</b>. This should be one of the values listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
KSPROPERTY_MEMBER_RANGES

</td>
<td>
Indicates that list members are ranges, of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff564394">KSPROPERTY_BOUNDS_LONG</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff564395">KSPROPERTY_BOUNDS_LONGLONG</a>.

</td>
</tr>
<tr>
<td>

<dl>
<dt>KSPROPERTY_MEMBER</dt>
<dt>_STEPPEDRANGES</dt>
</dl>


</td>
<td>
Indicates that the following members are stepped values within ranges, of type <a href="https://msdn.microsoft.com/library/windows/hardware/dn936838">KSPROPERTY_STEPPING_LONG</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/dn936841">KSPROPERTY_STEPPING_LONGLONG</a>..

</td>
</tr>
<tr>
<td>
KSPROPERTY_MEMBER_VALUES

</td>
<td>
Each entry in the members array is a single value.

</td>
</tr>
</table>
 


## -remarks



The size of the array can be determined by multiplying <b>MembersCount</b> by <b>MembersSize</b>.

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff565190">KSPROPERTY_MEMBERSLIST</a> structure contains a KSPROPERTY_MEMBERSHEADER structure as its first member. The second member, <b>Members</b>, points to an array of property values or ranges.

In addition, a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565132">KSPROPERTY_DESCRIPTION</a> structure can be followed by a list of KSPROPERTY_MEMBERSHEADER structures.

For more information about KSPROPERTY_MEMBER_FLAG_DEFAULT, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565176">KSPROPERTY_ITEM</a>. For more information about KSPROPERTY_MEMBER_FLAG_BASICSUPPORT_MULTICHANNEL and KSPROPERTY_MEMBER_FLAG_BASICSUPPORT_UNIFORM, see <a href="https://msdn.microsoft.com/48ee3b33-fb97-4e71-bf6f-5dbdb76aa7f8">Exposing Multichannel Nodes</a> in the Windows Driver Kit (WDK) Audio documentation. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564394">KSPROPERTY_BOUNDS_LONG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564395">KSPROPERTY_BOUNDS_LONGLONG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565132">KSPROPERTY_DESCRIPTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565176">KSPROPERTY_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565190">KSPROPERTY_MEMBERSLIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn936838">KSPROPERTY_STEPPING_LONG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn936841">KSPROPERTY_STEPPING_LONGLONG</a>
 

 

