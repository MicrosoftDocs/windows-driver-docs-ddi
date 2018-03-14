---
UID: NF:ntifs.SeSetSecurityDescriptorInfoEx
title: SeSetSecurityDescriptorInfoEx function
author: windows-driver-content
description: The SeSetSecurityDescriptorInfoEx routine modifies an object's security descriptor and specifies whether the object supports automatic inheritance of access control entries (ACE).
old-location: ifsk\sesetsecuritydescriptorinfoex.htm
old-project: ifsk
ms.assetid: 90526705-069d-432f-87b1-1efc247aee05
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: SeSetSecurityDescriptorInfoEx, SeSetSecurityDescriptorInfoEx routine [Installable File System Drivers], ifsk.sesetsecuritydescriptorinfoex, ntifs/SeSetSecurityDescriptorInfoEx, seref_d3965072-a36e-478c-9c57-5614920d69c8.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
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
-	SeSetSecurityDescriptorInfoEx
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SeSetSecurityDescriptorInfoEx function


## -description


The <b>SeSetSecurityDescriptorInfoEx</b> routine modifies an object's security descriptor and specifies whether the object supports automatic inheritance of access control entries (ACE).


## -syntax


````
NTSTATUS SeSetSecurityDescriptorInfoEx(
  _In_opt_ PVOID                 Object,
  _In_     PSECURITY_INFORMATION SecurityInformation,
  _In_     PSECURITY_DESCRIPTOR  SecurityDescriptor,
  _Inout_  PSECURITY_DESCRIPTOR  *ObjectsSecurityDescriptor,
  _In_     ULONG                 AutoInheritFlags,
  _In_     POOL_TYPE             PoolType,
  _In_     PGENERIC_MAPPING      GenericMapping
);
````


## -parameters




### -param Object [in, optional]

Pointer to the object whose security descriptor is to be modified. This is used to update security quota information.


### -param SecurityInformation [in]

Pointer to a value specifying which security information is to be set. Can be a combination of one or more of the following. 

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

TBD


### -param ObjectsSecurityDescriptor [in, out]

Pointer to a pointer to the object's security descriptor. The security descriptor must be in self-relative format. This structure must be deallocated by the caller.


### -param AutoInheritFlags [in]

Bitmask that controls automatic inheritance of ACEs. Set to the logical OR of one or more of the following bit flags: 

<table>
<tr>
<th>Security Information Flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
SEF_DACL_AUTO_INHERIT

</td>
<td>
If this flag is set, the DACL is treated as an auto-inherit DACL and is processed as described in the following Remarks section. This bit is ignored if DACL_SECURITY_INFORMATION is not set in the <i>SecurityInformation</i> parameter.

</td>
</tr>
<tr>
<td>
SEF_SACL_AUTO_INHERIT

</td>
<td>
If this flag is set, the SACL is treated as an auto-inherit SACL and is processed as described in the following Remarks section. This bit is ignored if SACL_SECURITY_INFORMATION is not set in the <i>SecurityInformation</i> parameter.

</td>
</tr>
</table>
 


### -param PoolType [in]

Specifies the pool type to use when allocating a new security descriptor, which can be one of the following: 

<ul>
<li><b>NonPagedPool</b></li>
<li><b>PagedPool</b></li>
<li><b>NonPagedPoolCacheAligned</b></li>
<li><b>PagedPoolCacheAligned</b></li>
</ul>
Usually, a caller specifies <b>PagedPool</b>, or else <b>NonPagedPool</b> if the buffer will be accessed at IRQL &gt;= DISPATCH_LEVEL or in an arbitrary thread context. 

<b>Note</b>: The <b>NonPagedPoolMustSucceed</b> and <b>NonPagedPoolCacheAlignedMustS</b> pool types are obsolete and should no longer be used. 


### -param GenericMapping [in]

Pointer to a GENERIC_MAPPING structure that specifies the mapping of generic to specific and standard access types for the object being accessed. This mapping structure is expected to be safe to access (that is, captured if necessary) prior to be passed to this routine.


#### - SecurityDescriptor [in]

The input security descriptor to be applied to the object. The caller of this routine is expected to probe and capture the passed security descriptor before calling, and to release it after calling.


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



If the <i>AutoInheritFlags</i> parameter is zero, the effect of calling <b>SeSetSecurityDescriptorInfoEx</b> is the same as that of calling <b>SeSetSecurityDescriptorInfo</b>.

If <i>AutoInheritFlags</i> specifies the SEF_DACL_AUTO_INHERIT bit, <b>SeSetSecurityDescriptorInfoEx</b> applies the following rules to the DACL to create the new security descriptor from the current descriptor:

<ul>
<li>
If the SE_DACL_PROTECTED flag is not set in the control bits of the either the current security descriptor or the input <i>SecurityDescriptor</i>, <b>SeSetSecurityDescriptorInfoEx</b> constructs the output security descriptor from the inherited ACEs of the current security descriptor and noninherited ACEs of <i>SecurityDescriptor</i>. That is, it is impossible to change an inherited ACE by changing the ACL on an object. This behavior preserves the inherited ACEs as they were inherited from the parent container. 

</li>
<li>
If SE_DACL_PROTECTED is set in the input <i>SecurityDescriptor</i>, the current security descriptor is ignored. The output security descriptor is built as a copy of the input <i>SecurityDescriptor</i> with any INHERITED_ACE bits turned off. 

Ideally an ACL editor should turn off the INHERITED_ACE bits indicating to its caller that the ACEs inherited from the object's parent are now being explicitly set on the object. 

</li>
<li>
If SE_DACL_PROTECTED is set in the current security descriptor and not in the <i>SecurityDescriptor</i>, the current security descriptor is ignored. The output security descriptor is built as a copy of the <i>SecurityDescriptor</i>. It is the caller's responsibility to ensure that the correct ACEs have the INHERITED_ACE bit turned on. 

</li>
</ul>
If <i>AutoInheritFlags</i> specifies the SEF_SACL_AUTO_INHERIT bit, <b>SeSetSecurityDescriptorInfoEx</b> applies similar rules to the new SACL.

For more information about access control and ACE inheritance, see the Security section of the Microsoft Windows SDK documentation.




## -see-also

<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>



<a href="..\ntifs\nf-ntifs-rtlcreatesecuritydescriptorrelative.md">RtlCreateSecurityDescriptorRelative</a>



<a href="..\ntifs\nf-ntifs-sequerysecuritydescriptorinfo.md">SeQuerySecurityDescriptorInfo</a>



<a href="..\wdm\nf-wdm-rtlvalidsecuritydescriptor.md">RtlValidSecurityDescriptor</a>



<a href="..\wdm\ns-wdm-_acl.md">ACL</a>



<a href="..\ntifs\nf-ntifs-sesetsecuritydescriptorinfo.md">SeSetSecurityDescriptorInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556635">SECURITY_INFORMATION</a>



<a href="..\wdm\nf-wdm-rtllengthsecuritydescriptor.md">RtlLengthSecurityDescriptor</a>



<a href="..\wdm\nf-wdm-rtlcreatesecuritydescriptor.md">RtlCreateSecurityDescriptor</a>



<a href="..\wdm\nf-wdm-rtlsetdaclsecuritydescriptor.md">RtlSetDaclSecurityDescriptor</a>



<a href="..\ntifs\nf-ntifs-rtlsetownersecuritydescriptor.md">RtlSetOwnerSecurityDescriptor</a>



<a href="..\wdm\ns-wdm-_generic_mapping.md">GENERIC_MAPPING</a>



 

 


