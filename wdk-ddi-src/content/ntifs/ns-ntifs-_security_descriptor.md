---
UID: NS:ntifs._SECURITY_DESCRIPTOR
title: _SECURITY_DESCRIPTOR (ntifs.h)
description: The SECURITY_DESCRIPTOR structure contains the security information associated with an object. Drivers use this structure to set and query an object's security status.
old-location: ifsk\security_descriptor.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["SECURITY_DESCRIPTOR structure"]
ms.keywords: "*PISECURITY_DESCRIPTOR, SECURITY_DESCRIPTOR, SECURITY_DESCRIPTOR structure [Installable File System Drivers], _SECURITY_DESCRIPTOR, ifsk.security_descriptor, ntifs/SECURITY_DESCRIPTOR, securitystructures_b3cd4d20-6abc-49e7-92dd-8dd707e973fa.xml"
req.header: ntifs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available starting with Microsoft Windows 2000.
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
targetos: Windows
req.typenames: SECURITY_DESCRIPTOR, *PISECURITY_DESCRIPTOR
f1_keywords:
 - _SECURITY_DESCRIPTOR
 - ntifs/_SECURITY_DESCRIPTOR
 - PISECURITY_DESCRIPTOR
 - ntifs/PISECURITY_DESCRIPTOR
 - SECURITY_DESCRIPTOR
 - ntifs/SECURITY_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - SECURITY_DESCRIPTOR
---

# _SECURITY_DESCRIPTOR structure


## -description

The SECURITY_DESCRIPTOR structure contains the security information associated with an object. Drivers use this structure to set and query an object's security status. 

Because the internal format of a security descriptor can vary, drivers are not to modify the SECURITY_DESCRIPTOR structure directly. For creating and manipulating a security descriptor, use the functions listed in the See Also section.

## -struct-fields

### -field Revision

Specifies the revision level of the security descriptor.

### -field Sbz1

Specifies a zero byte of padding that aligns the Revision member on a 16-bit boundary.

### -field Control

The control information of security descriptor. For more information, see [SECURITY_DESCRIPTOR_CONTROL](/windows-hardware/drivers/ifs/security-descriptor-control).

### -field Owner

A pointer to an owner security identifier.
> [!NOTE]
> This member might be invalid. You should use **RtlGetOwnerSecurityDescriptor** to get an owner security identifier.

### -field Group

A pointer to a primary group security identifier. 
> [!NOTE]
> This member might be invalid. You should use **RtlGetGroupSecurityDescriptor** to get this member.

### -field Sacl

A pointer to a system access control list (SACL). 
> [!NOTE]
> This member might be invalid. You should use **RtlGetSaclSecurityDescriptor** to get this member.

### -field Dacl

A pointer to a discretionary access control list (DACL). 
> [!NOTE]
> This member might be invalid. You should use **RtlGetDaclSecurityDescriptor** to get this member.

## -remarks

A security descriptor includes information that specifies the following components of an object's security: 
* An owner [SID](ns-ntifs-_sid.md)
* A primary group SID
* A discretionary [ACL](../wdm/ns-wdm-_acl.md) (DACL) 
* A system ACL (SACL)

## -see-also

[ACL](../wdm/ns-wdm-_acl.md)

[ObGetObjectSecurity](../wdm/nf-wdm-obgetobjectsecurity.md)

[ObReleaseObjectSecurity](../wdm/nf-wdm-obreleaseobjectsecurity.md)

[RtlCreateSecurityDescriptor](../wdm/nf-wdm-rtlcreatesecuritydescriptor.md)

[RtlGetDaclSecurityDescriptor](nf-ntifs-rtlgetdaclsecuritydescriptor.md)

[RtlGetGroupSecurityDescriptor](nf-ntifs-rtlgetgroupsecuritydescriptor.md)

[RtlGetOwnerSecurityDescriptor](nf-ntifs-rtlgetownersecuritydescriptor.md)

[RtlGetSaclSecurityDescriptor](nf-ntifs-rtlgetsaclsecuritydescriptor.md)

[RtlLengthSecurityDescriptor](../wdm/nf-wdm-rtllengthsecuritydescriptor.md)

[RtlSetDaclSecurityDescriptor](../wdm/nf-wdm-rtlsetdaclsecuritydescriptor.md)

[RtlSetGroupSecurityDescriptor](nf-ntifs-rtlsetgroupsecuritydescriptor.md)

[RtlSetOwnerSecurityDescriptor](nf-ntifs-rtlsetownersecuritydescriptor.md)

[RtlValidSecurityDescriptor](../wdm/nf-wdm-rtlvalidsecuritydescriptor.md)

[SECURITY_DESCRIPTOR_CONTROL](/windows-hardware/drivers/ifs/security-descriptor-control)

[SECURITY_INFORMATION](/windows-hardware/drivers/ifs/security-information)

[SID](ns-ntifs-_sid.md)

[SeAccessCheck](../wdm/nf-wdm-seaccesscheck.md)

[SeAssignSecurity](../wdm/nf-wdm-seassignsecurity.md)

[SeAssignSecurityEx](../wdm/nf-wdm-seassignsecurityex.md)

[SeDeassignSecurity](../wdm/nf-wdm-sedeassignsecurity.md)

[SeSetSecurityDescriptorInfo](nf-ntifs-sesetsecuritydescriptorinfo.md)

[SeSetSecurityDescriptorInfoEx](nf-ntifs-sesetsecuritydescriptorinfoex.md)

[SeValidSecurityDescriptor](../wdm/nf-wdm-sevalidsecuritydescriptor.md)

[ZwQuerySecurityObject](nf-ntifs-zwquerysecurityobject.md)

[ZwSetSecurityObject](nf-ntifs-zwsetsecurityobject.md)
