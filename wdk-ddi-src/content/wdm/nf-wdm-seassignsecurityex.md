---
UID: NF:wdm.SeAssignSecurityEx
title: SeAssignSecurityEx function
author: windows-driver-content
description: The SeAssignSecurityEx routine builds a self-relative security descriptor for a new object given the following optional parameters:\_a security descriptor of the object's parent directory, an explicit security descriptor for the object, and the object type.
old-location: kernel\seassignsecurityex.htm
old-project: kernel
ms.assetid: 94f6d3a3-7f0d-4f57-8240-3c4a10cf4488
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: k110_e014ad32-3cbd-47e6-908b-65357203ee59.xml, SeAssignSecurityEx, kernel.seassignsecurityex, wdm/SeAssignSecurityEx, SeAssignSecurityEx routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	SeAssignSecurityEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# SeAssignSecurityEx function


## -description


The 
   <b>SeAssignSecurityEx</b> routine builds a self-relative security descriptor for a new object given the following optional parameters: a security descriptor of the object's parent directory, an explicit security descriptor for the object, and the object type.


## -syntax


````
NTSTATUS SeAssignSecurityEx(
  _In_opt_ PSECURITY_DESCRIPTOR      ParentDescriptor,
  _In_opt_ PSECURITY_DESCRIPTOR      ExplicitDescriptor,
  _Out_    PSECURITY_DESCRIPTOR      *NewDescriptor,
  _In_opt_ GUID                      *ObjectType,
  _In_     BOOLEAN                   IsDirectoryObject,
  _In_     ULONG                     AutoInheritFlags,
  _In_     PSECURITY_SUBJECT_CONTEXT SubjectContext,
  _In_     PGENERIC_MAPPING          GenericMapping,
  _In_     POOL_TYPE                 PoolType
);
````


## -parameters




### -param ParentDescriptor [in, optional]

Pointer to the <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> of the parent object that contains the new object being created. <i>ParentDescriptor</i> can be <b>NULL</b>, or have a <b>NULL</b> system access control list (<a href="https://msdn.microsoft.com/5f6fec1a-1134-4765-81be-9b50939e5e66">SACL</a>) or a <b>NULL</b> discretionary access control list (<a href="https://msdn.microsoft.com/86688b5d-575d-42e1-9158-7ffba1aaf1d3">DACL</a>).


### -param ExplicitDescriptor [in, optional]

Pointer to an explicit <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> that is applied to the new object. <i>ExplicitDescriptor</i> can be <b>NULL</b>, or have a <b>NULL</b> SACL or a <b>NULL</b> DACL.


### -param NewDescriptor [out]

Receives a pointer to the returned <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>.  <b>SeAssignSecurityEx</b> allocates the buffer from the paged memory pool.


### -param ObjectType [in, optional]

Pointer to a GUID for the type of object being created. If the object does not have a GUID, <i>ObjectType</i> must be set to <b>NULL</b>.


### -param IsDirectoryObject [in]

Specifies whether the new object is a directory object. If <i>IsDirectoryObject</i> is set to <b>TRUE</b>, the new object is a directory object, otherwise the new object is not a directory object.


### -param AutoInheritFlags [in]

Specifies the type of automatic inheritance that is applied to access control entries (<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>) in the access control lists (<a href="https://msdn.microsoft.com/library/windows/hardware/ff538866">ACL</a>) specified by <i>ParentDescriptor</i>. <i>AutoInheritFlags</i> also controls privilege checking, owner checking, and setting a default owner and group for <i>NewDescriptor</i>. <i>AutoInheritFlags</i> must be set to a logical OR of one or more of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
SEF_DACL_AUTO_INHERIT

</td>
<td>
ACEs in the DACL of <i>ParentDescriptor</i> are inherited by <i>NewDescripto</i>r, in addition to explicit ACEs specified by <i>ExplicitDescriptor</i>.

</td>
</tr>
<tr>
<td>
SEF_SACL_AUTO_INHERIT

</td>
<td>
ACEs in the SACL of <i>ParentDescriptor</i> are inherited by <i>NewDescriptor</i>, in addition to explicit ACEs specified by <i>ExplicitDescriptor</i>.

</td>
</tr>
<tr>
<td>
SEF_DEFAULT_DESCRIPTOR_FOR_OBJECT

</td>
<td>
<i>ExplicitDescriptor</i> is the default descriptor for the object type specified by <i>ObjectType</i>. <i>ExplicitDescriptor</i> is not used if ACEs are inherited from <i>ParentDescriptor</i>.

</td>
</tr>
<tr>
<td>
SEF_AVOID_PRIVILEGE_CHECK

</td>
<td>
Privilege checking is not done. This flag is useful with automatic inheritance because it avoids privilege checking on each child that needs to be updated. 

</td>
</tr>
<tr>
<td>
SEF_AVOID_OWNER_CHECK

</td>
<td>
Owner checking is not done.

</td>
</tr>
<tr>
<td>
SEF_DEFAULT_OWNER_FROM_PARENT

</td>
<td>
If an owner is specified by <i>ExplicitDescriptor</i>, this flag is not used, and the owner of <i>NewDescriptor</i> is set to the owner specified by <i>ExplictDescriptor</i>.

If an owner is not specified by <i>ExplicitDescriptor</i>, this flag is used in the following way: If the flag is set, the owner of <i>NewDescriptor</i> is set to the owner of <i>ParentDescriptor</i>. Otherwise, the owner of <i>NewDescriptor</i> is set to the owner specified by the <i>SubjectContext.</i>

</td>
</tr>
<tr>
<td>
SEF_DEFAULT_GROUP_FROM_PARENT

</td>
<td>
If a group is specified by <i>ExplicitDescriptor</i>, this flag is not used, and the group of <i>NewDescriptor</i> is set to the group specified by <i>ExplictDescriptor</i>.

If a group is not specified by <i>ExplicitDescriptor</i>, this flag is used in the following way: If the flag is set, the group of <i>NewDescriptor</i> is set to the group of <i>ParentDescriptor</i>. Otherwise, the group of <i>NewDescriptor</i> is set to the group specified by the <i>SubjectContext.</i>

</td>
</tr>
</table>
 

The assignment of system and discretionary ACLs is described in the following table:

<table>
<tr>
<th></th>
<th>Nondefault explicit descriptor(1)</th>
<th>Default explicit descriptor(2)</th>
<th><b>NULL</b> Explicit descriptor</th>
</tr>
<tr>
<td>
ACL is inherited from parent descriptor(3).

</td>
<td>
Assign both inherited and explicit ACLs(5)(6).

</td>
<td>
Assign inherited ACL.

</td>
<td>
Assign inherited ACL.

</td>
</tr>
<tr>
<td>
ACL is not inherited from parent descriptor(4).

</td>
<td>
Assign nondefault ACL.

</td>
<td>
Assign default ACL.

</td>
<td>
Assign no ACL.

</td>
</tr>
</table>
 

<b>Assignment Notes</b>

<ol>
<li>
The SEF_DEFAULT_DESCRIPTOR_FOR_OBJECT flag is not specified.

</li>
<li>
The SEF_DEFAULT_DESCRIPTOR_FOR_OBJECT flag is specified.

</li>
<li>
The auto inherit flag for an ACL is specified (SEF_DACL_AUTO_INHERIT or SEF_SACL_AUTO_INHERIT).

</li>
<li>
The automatic inherit flag for an ACL is not specified.

</li>
<li>
ACEs with the INHERITED_ACE bit set in their <b>AceFlags</b> member are <u>not</u> copied to the assigned security descriptor. 

</li>
<li>
ACEs that are inherited from the parent descriptor are appended after the ACEs specified by the explicit descriptor.

</li>
</ol>

### -param SubjectContext [in]

Pointer to a security context of the subject that is creating the object. <i>SubjectContext</i> is used to retrieve default security information for the new object, including the default owner, the primary group, and discretionary access control.


### -param GenericMapping [in]

Pointer to an array of access mask values that specify the mapping between each generic rights to object-specific rights.


### -param PoolType [in]

This parameter is unused.  The buffer to hold the new security descriptor is always allocated from paged pool.


## -returns



<b>SeAssignSecurityEx</b> returns one of the following values:

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
The assignment was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_OWNER</b></dt>
</dl>
</td>
<td width="60%">
The SID provided as the owner of the new security descriptor is not a SID that the caller is authorized to assign as the owner of an object. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PRIVILEGE_NOT_HELD</b></dt>
</dl>
</td>
<td width="60%">
The caller does not have the privilege (<b>SeSecurityPrivilege</b>) necessary to explicitly assign the specified SACL.

</td>
</tr>
</table>
 




## -remarks



<b>SeAssignSecurityEx</b> extends the basic operation of <b>SeAssignSecurity</b> in the following ways:

<ul>
<li>
<i>ObjectType</i> optionally specifies an object type. Object-specific inheritance is controlled by the following members of an object-specific ACE: <b>Flags</b>, <b>InheritedObjectType</b>, and <b>Header.AceFlags</b>.

</li>
<li>
<i>AutoInheritFlags </i>specifies the type of automatic inheritance of ACEs that is used. AutoInheritFlags also controls privilege checking, owner checking, and setting a default owner and group for <i>NewDescriptor</i>.

</li>
</ul>
For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also

<a href="..\wdm\nf-wdm-sedeassignsecurity.md">SeDeassignSecurity</a>



<a href="..\wdm\ns-wdm-_generic_mapping.md">GENERIC_MAPPING</a>



<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>



<a href="..\wdm\nf-wdm-seassignsecurity.md">SeAssignSecurity</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20SeAssignSecurityEx routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

