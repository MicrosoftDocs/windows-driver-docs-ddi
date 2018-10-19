---
UID: NF:wdm.SeAccessCheck
title: SeAccessCheck function
author: windows-driver-content
description: The SeAccessCheck routine determines whether the requested access rights can be granted to an object protected by a security descriptor and an object owner.
old-location: kernel\seaccesscheck.htm
tech.root: kernel
ms.assetid: 90726c66-738f-416f-993a-84cbf2eb67d2
ms.date: 04/30/2018
ms.keywords: SeAccessCheck, SeAccessCheck routine [Kernel-Mode Driver Architecture], k110_7d3f1afa-5728-4ade-8915-aeb77dc3edd3.xml, kernel.seaccesscheck, wdm/SeAccessCheck
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	SeAccessCheck
product:
- Windows
targetos: Windows
req.typenames: 
---

# SeAccessCheck function


## -description



   The <b>SeAccessCheck</b> routine determines whether the requested access rights can be granted to an object protected by a security descriptor and an object owner.


## -parameters




### -param SecurityDescriptor [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a> structure that describes the security descriptor protecting the object being accessed. 


### -param SubjectSecurityContext [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563714">SECURITY_SUBJECT_CONTEXT</a> structure that specifies the subject's captured security context.


### -param SubjectContextLocked [in]

Indicates whether the user's subject context is locked, so that it does not have to be locked again.


### -param DesiredAccess [in]

Specifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> bitmask for the access rights that the caller is attempting to acquire.  If the caller sets the MAXIMUM_ALLOWED bit, the routine performs all DACL checks. However, the routine does not do any privilege checks, unless the caller specifically requests them by setting the ACCESS_SYSTEM_SECURITY or WRITE_OWNER bits.


### -param PreviouslyGrantedAccess [in]

Specifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> bitmask of access rights already granted, such as access rights granted as a result of holding a privilege.


### -param Privileges [out]

Pointer to a caller-supplied variable to be set to the address of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551860">PRIVILEGE_SET</a> structure that will be used as part of the access validation, or this parameter can be <b>NULL</b>. The returned buffer, if any, must be released by the caller with <a href="https://msdn.microsoft.com/library/windows/hardware/ff556656">SeFreePrivileges</a>.


### -param GenericMapping [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546526">GENERIC_MAPPING</a> structure associated with this object type. This value specifies the specific access rights implied by each GENERIC_<i>XXX</i> access right.


### -param AccessMode [in]

Specifies the access mode to be used in the check, either <b>UserMode</b> or <b>KernelMode</b>.


### -param GrantedAccess [out]

Pointer to a returned access mask indicating the granted access. If the caller specifies MAXIMUM_ALLOWED, and the DACL in <i>SecurityDescriptor</i> is <b>NULL</b>, then the routine returns GENERIC_ALL plus any additional access the caller explicitly requests.


### -param AccessStatus [out]

Pointer to the status value indicating why access was denied.


## -returns



If access is allowed, <b>SeAccessCheck</b> returns <b>TRUE</b>.




## -remarks



<b>SeAccessCheck</b> might perform privilege tests for <b>SeTakeOwnershipPrivilege</b> and <b>SeSecurityPrivilege</b>, depending on the accesses being requested. It might perform additional privilege testing in future releases of the operating system.

This routine also might check whether the caller is the owner of the object in order to grant WRITE_DAC or READ_CONTROL access.

If this routine returns <b>FALSE</b>, the caller should use the returned <i>AccessStatus</i> as its return value. That is, the caller should avoid hardcoding a return value of STATUS_ACCESS_DENIED or any other specific STATUS_<i>XXX</i> value. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546526">GENERIC_MAPPING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549231">IoGetFileObjectGenericMapping</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551860">PRIVILEGE_SET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563714">SECURITY_SUBJECT_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556656">SeFreePrivileges</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563793">SeValidSecurityDescriptor</a>
 

 

