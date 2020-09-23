---
UID: NF:wdm.SeAssignSecurity
title: SeAssignSecurity function (wdm.h)
description: The SeAssignSecurity routine builds a self-relative security descriptor for a new object, given the security descriptor of its parent directory and any originally requested security for the object.
old-location: kernel\seassignsecurity.htm
tech.root: kernel
ms.assetid: 08f0b4c0-ba77-450d-8b93-73231bbf760c
ms.date: 04/30/2018
keywords: ["SeAssignSecurity function"]
ms.keywords: SeAssignSecurity, SeAssignSecurity routine [Kernel-Mode Driver Architecture], k110_10d67a00-4643-4d40-b9a2-1a19e79dc755.xml, kernel.seassignsecurity, wdm/SeAssignSecurity
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - SeAssignSecurity
 - wdm/SeAssignSecurity
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - SeAssignSecurity
---

# SeAssignSecurity function


## -description

The 
   <b>SeAssignSecurity</b> routine builds a self-relative security descriptor for a new object, given the security descriptor of its parent directory and any originally requested security for the object.

## -parameters

### -param ParentDescriptor 

[in, optional]
Pointer to a buffer containing the <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a> for the parent directory, if any, containing the new object being created. <i>ParentDescriptor</i> can be <b>NULL</b>, or have a <b>NULL</b> system access control list (<a href="/windows-hardware/drivers/">SACL</a>) or a <b>NULL</b> discretionary access control list (<a href="/windows-hardware/drivers/">DACL</a>).

### -param ExplicitDescriptor 

[in, optional]
Pointer to a buffer containing the <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a> specified by the user that is applied to the new object. <i>ExplicitDescriptor</i> can be <b>NULL</b>, or have a <b>NULL</b> SACL or a <b>NULL</b> DACL.

### -param NewDescriptor 

[out]
Receives a pointer to the returned <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>. <b>SeAssignSecurity</b> allocates the buffer from the paged memory pool.

### -param IsDirectoryObject 

[in]
Specifies whether the new object is a directory object. <b>TRUE</b> indicates the object contains other objects.

### -param SubjectContext 

[in]
Pointer to a buffer containing the security context of the subject creating the object. This is used to retrieve default security information for the new object, such as the default owner, the primary group, and discretionary access control.

### -param GenericMapping 

[in]
Pointer to the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_generic_mapping">GENERIC_MAPPING</a> structure that describes the mapping from each generic right to the implied nongeneric rights.

### -param PoolType 

[in]
This parameter is unused.  The buffer to hold the new security descriptor is always allocated from paged pool.

## -returns

<b>SeAssignSecurity</b> can return one of the following:

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
The SID provided for the owner of the target security descriptor is not one the caller is authorized to assign as the owner of an object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PRIVILEGE_NOT_HELD</b></dt>
</dl>
</td>
<td width="60%">
The caller does not have the privilege (<b>SeSecurityPrivilege</b>) necessary to explicitly assign the specified system ACL.

</td>
</tr>
</table>

## -remarks

The final security descriptor returned to the caller may contain a mix of information, some explicitly provided from the new object's parent.

<b>SeAssignSecurity</b> assumes privilege checking has not been performed. This routine performs privilege checking.

The assignment of system and discretionary ACLs is governed by the logic illustrated in the following table:

<table>
<tr>
<th></th>
<th>Explicit (nondefault) ACL specified</th>
<th>Explicit default ACL specified</th>
<th>No ACL specified</th>
</tr>
<tr>
<td>
<b>Inheritable ACL from parent
              </b>

</td>
<td>
Assign specified ACL

</td>
<td>
Assign inherited ACL

</td>
<td>
Assign inherited ACL

</td>
</tr>
<tr>
<td>
<b>No inheritable ACL from parent</b>

</td>
<td>
Assign specified ACL

</td>
<td>
Assign default ACL

</td>
<td>
Assign no ACL

</td>
</tr>
</table>
 

An explicitly specified ACL, whether a default ACL or not, can be empty or null. The caller must be a kernel-mode client or be appropriately privileged to explicitly assign a default or nondefault system ACL.

The assignment of the new object's owner and group is governed by the following logic:

<ul>
<li>
If the passed security descriptor includes an owner, it is assigned as the new object's owner. Otherwise, the caller's token is considered to determine the owner. Within the token, the default owner, if any, is assigned. Otherwise, the caller's user ID is assigned.

</li>
<li>
If the passed security descriptor includes a group, it is assigned as the new object's group. Otherwise, the caller's token is considered to determine the group. Within the token, the default group, if any, is assigned. Otherwise, the caller's primary group ID is assigned.

</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_generic_mapping">GENERIC_MAPPING</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iogetfileobjectgenericmapping">IoGetFileObjectGenericMapping</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-sedeassignsecurity">SeDeassignSecurity</a>