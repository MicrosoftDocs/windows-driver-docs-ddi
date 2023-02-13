---
UID: NF:wdm.SeAccessCheck
title: SeAccessCheck function (wdm.h)
description: The SeAccessCheck routine determines whether the requested access rights can be granted to an object protected by a security descriptor and an object owner.
old-location: kernel\seaccesscheck.htm
tech.root: kernel
ms.date: 02/13/2023
keywords: ["SeAccessCheck function"]
ms.keywords: SeAccessCheck, SeAccessCheck routine [Kernel-Mode Driver Architecture], k110_7d3f1afa-5728-4ade-8915-aeb77dc3edd3.xml, kernel.seaccesscheck, wdm/SeAccessCheck
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
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
 - SeAccessCheck
 - wdm/SeAccessCheck
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - SeAccessCheck
---

# SeAccessCheck function

## -description

**SeAccessCheck** determines whether the requested access rights can be granted to an object protected by a security descriptor and an object owner.

## -parameters

### -param SecurityDescriptor [in]

Pointer to the [**SECURITY_DESCRIPTOR**](../ntifs/ns-ntifs-_security_descriptor.md) structure that describes the security descriptor protecting the object being accessed.

### -param SubjectSecurityContext [in]

Pointer to the opaque [**SECURITY_SUBJECT_CONTEXT**](/windows-hardware/drivers/kernel/eprocess) structure that specifies the subject's captured security context.

### -param SubjectContextLocked [in]

Boolean value that indicates whether the user's subject context is locked, so that it does not have to be locked again.

### -param DesiredAccess [in]

Specifies the [**ACCESS_MASK**](/windows-hardware/drivers/kernel/access-mask) bitmask for the access rights that the caller is attempting to acquire.  If the caller sets the MAXIMUM_ALLOWED bit, the routine performs all DACL checks. However, **SeAccessCheck** does not do any privilege checks unless the caller specifically requests them by setting the ACCESS_SYSTEM_SECURITY or WRITE_OWNER bits.

### -param PreviouslyGrantedAccess [in]

Specifies the [**ACCESS_MASK**](/windows-hardware/drivers/kernel/access-mask) bitmask of access rights already granted, such as access rights granted as a result of holding a privilege.

### -param Privileges [out]

Pointer to a caller-supplied variable to be set to the address of the [**PRIVILEGE_SET**](ns-wdm-_privilege_set.md) structure that will be used as part of the access validation, or this parameter can be NULL. The returned buffer, if any, must be released by the caller with [**SeFreePrivileges**](../ntifs/nf-ntifs-sefreeprivileges.md).

### -param GenericMapping [in]

Pointer to the [**GENERIC_MAPPING**](ns-wdm-_generic_mapping.md) structure associated with this object type. This value specifies the specific access rights implied by each GENERIC_*XXX* access right.

### -param AccessMode [in]

Specifies the access mode to be used in the check, either **UserMode** or **KernelMode**.

### -param GrantedAccess [out]

Pointer to a returned access mask indicating the granted access. If the caller specifies MAXIMUM_ALLOWED, and the DACL in **SecurityDescriptor** is NULL, then the routine returns GENERIC_ALL plus any additional access the caller explicitly requests.

### -param AccessStatus [out]

Pointer to the status value indicating why access was denied.

## -returns

If access is allowed, **SeAccessCheck** returns TRUE.

## -remarks

**SeAccessCheck** might perform privilege tests for [**SeTakeOwnershipPrivilege** and **SeSecurityPrivilege**](../ntifs/ns-ntifs-_se_exports.md), depending on the accesses being requested. It might perform additional privilege testing in future releases of the operating system.

This routine also might check whether the caller is the owner of the object in order to grant WRITE_DAC or READ_CONTROL access.

If this routine returns FALSE, the caller should use the returned **AccessStatus** as its return value. That is, the caller should avoid hardcoding a return value of STATUS_ACCESS_DENIED or any other specific STATUS_*XXX* value.

For more information about security and access control, see [Windows security model for driver developers](/windows-hardware/drivers/driversecurity/windows-security-model) and the documentation on these topics in the Microsoft Windows SDK.

## -see-also

[**ACCESS_MASK**](/windows-hardware/drivers/kernel/access-mask)

[**GENERIC_MAPPING**](ns-wdm-_generic_mapping.md)

[**IoGetFileObjectGenericMapping**](../ntddk/nf-ntddk-iogetfileobjectgenericmapping.md)

[**PRIVILEGE_SET**](ns-wdm-_privilege_set.md)

[**SE_EXPORTS**](../ntifs/ns-ntifs-_se_exports.md)

[**SECURITY_DESCRIPTOR**](../ntifs/ns-ntifs-_security_descriptor.md)

[**SECURITY_SUBJECT_CONTEXT**](/windows-hardware/drivers/kernel/eprocess)

[**SeFreePrivileges**](../ntifs/nf-ntifs-sefreeprivileges.md)

[**SeValidSecurityDescriptor**](nf-wdm-sevalidsecuritydescriptor.md)
