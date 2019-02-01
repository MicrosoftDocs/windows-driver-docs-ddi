---
UID: NF:ntifs.SeSetSecurityDescriptorInfo
title: SeSetSecurityDescriptorInfo function (ntifs.h)
description: The SeSetSecurityDescriptorInfo routine sets an object's security descriptor.
old-location: ifsk\sesetsecuritydescriptorinfo.htm
tech.root: ifsk
ms.assetid: d6f02142-1cd8-4f09-b106-d963bf080495
ms.date: 04/16/2018
ms.keywords: SeSetSecurityDescriptorInfo, SeSetSecurityDescriptorInfo routine [Installable File System Drivers], ifsk.sesetsecuritydescriptorinfo, ntifs/SeSetSecurityDescriptorInfo, seref_061b8609-a537-4ccb-aa60-50a46b08e97f.xml
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	SeSetSecurityDescriptorInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# SeSetSecurityDescriptorInfo function


## -description


The <b>SeSetSecurityDescriptorInfo</b> routine sets an object's security descriptor.


## -parameters




### -param Object [in, optional]

Pointer to the object whose security descriptor is to be set. This is used to update security quota information.


### -param SecurityInformation [in]

Pointer to a bitmask specifying which security information is to be applied to the object. Can be a combination of one or more of the following values. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DACL_SECURITY_INFORMATION

</td>
<td>
Indicates the discretionary access control list (DACL) of the object is being set. Requires WRITE_DAC access. 

</td>
</tr>
<tr>
<td>
GROUP_SECURITY_INFORMATION

</td>
<td>
Indicates the primary group identifier of the object is being set. Requires WRITE_OWNER access. 

</td>
</tr>
<tr>
<td>
OWNER_SECURITY_INFORMATION

</td>
<td>
Indicates the owner identifier of the object is being set. Requires WRITE_OWNER access. 

</td>
</tr>
<tr>
<td>
SACL_SECURITY_INFORMATION

</td>
<td>
Indicates the system ACL (SACL) of the object is being set. Requires ACCESS_SYSTEM_SECURITY access. 

</td>
</tr>
</table>
 


### -param ModificationDescriptor

<p>The input security descriptor to be applied to the object. The caller of this routine is expected to probe and capture the passed security descriptor before calling <b>SeSetSecurityDescriptorInfo</b>, and to release it afterward.</p>


### -param ObjectsSecurityDescriptor [in, out]

Pointer to a pointer to the object's security descriptor. The security descriptor must be in self-relative format. The caller is responsible for freeing this structure when it is no longer needed.


### -param PoolType [in]

Specifies the pool type to use when allocating a new security descriptor, which can be one of the following: 

<ul>
<li><b>NonPagedPool</b></li>
<li><b>PagedPool</b></li>
<li><b>NonPagedPoolCacheAligned</b></li>
<li><b>PagedPoolCacheAligned</b></li>
</ul>
Usually, a caller specifies <b>PagedPool</b>, or else <b>NonPagedPool</b> if the buffer will be accessed at IRQL &gt;= DISPATCH_LEVEL or in an arbitrary thread context. 

<div class="alert"><b>Note</b>    The <b>NonPagedPoolMustSucceed</b> and <b>NonPagedPoolCacheAlignedMustS</b> pool types are obsolete and should no longer be used. </div>
<div> </div>

### -param GenericMapping [in]

Pointer to a GENERIC_MAPPING structure that specifies the mapping of generic to specific and standard access types for the object being accessed. This mapping structure is expected to be safe to access (that is, captured if necessary) prior to be passed to this routine.


## -returns



<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The object's security descriptor was successfully modified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BAD_DESCRIPTOR_FORMAT</b></dt>
</dl>
</td>
<td width="60%">
The provided object's security descriptor was not in self-relative format.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_SECURITY_ON_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The object does not have a security descriptor.

</td>
</tr>
</table>
 




## -remarks



<b>SeSetSecurityDescriptorInfo</b> modifies an object's existing security descriptor. If the object does not have a security descriptor, the call to <b>SeSetSecurityDescriptorInfo</b> will fail.

To specify whether the object supports automatic inheritance of access control entries (ACE), use <b>SeSetSecurityDescriptorInfoEx</b>.

A security descriptor can be in absolute or self-relative form. In self-relative form, all members of the structure are located contiguously in memory. In absolute form, the structure only contains pointers to the members.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538866">ACL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546526">GENERIC_MAPPING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561827">RtlCreateSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552165">RtlCreateSecurityDescriptorRelative</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562025">RtlLengthSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562781">RtlSetDaclSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553220">RtlSetOwnerSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563024">RtlValidSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556635">SECURITY_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556692">SeQuerySecurityDescriptorInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556707">SeSetAccessStateGenericMapping</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556712">SeSetSecurityDescriptorInfoEx</a>
 

 

