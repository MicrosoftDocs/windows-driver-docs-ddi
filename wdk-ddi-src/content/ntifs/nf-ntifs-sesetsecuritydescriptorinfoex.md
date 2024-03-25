---
UID: NF:ntifs.SeSetSecurityDescriptorInfoEx
title: SeSetSecurityDescriptorInfoEx function (ntifs.h)
description: Learn more about the SeSetSecurityDescriptorInfoEx function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["SeSetSecurityDescriptorInfoEx function"]
ms.keywords: SeSetSecurityDescriptorInfoEx, SeSetSecurityDescriptorInfoEx routine [Installable File System Drivers], ifsk.sesetsecuritydescriptorinfoex, ntifs/SeSetSecurityDescriptorInfoEx, seref_d3965072-a36e-478c-9c57-5614920d69c8.xml
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
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
targetos: Windows
req.typenames: 
f1_keywords:
 - SeSetSecurityDescriptorInfoEx
 - ntifs/SeSetSecurityDescriptorInfoEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - SeSetSecurityDescriptorInfoEx
---

# SeSetSecurityDescriptorInfoEx function

## -description

The **SeSetSecurityDescriptorInfoEx** routine modifies an object's security descriptor and specifies whether the object supports automatic inheritance of access control entries (ACE).

## -parameters

### -param Object [in, optional]

Pointer to the object whose security descriptor is to be modified. This is used to update security quota information.

### -param SecurityInformation [in]

Pointer to a value specifying which security information is to be set. Can be a combination of one or more of the following.

| Value | Meaning |
| ----- | ------- |
| DACL_SECURITY_INFORMATION | Indicates the discretionary access control list (DACL) of the object is being set. Requires WRITE_DAC access. |
| GROUP_SECURITY_INFORMATION | Indicates the primary group identifier of the object is being set. Requires WRITE_OWNER access. |
| OWNER_SECURITY_INFORMATION | Indicates the owner identifier of the object is being set. Requires WRITE_OWNER access. |
| SACL_SECURITY_INFORMATION | Indicates the system ACL (SACL) of the object is being set. Requires ACCESS_SYSTEM_SECURITY access. |

### -param ModificationDescriptor

The input security descriptor to be applied to the object. The caller of this routine is expected to probe and capture the passed security descriptor before calling, and to release it after calling.

### -param ObjectsSecurityDescriptor [in, out]

Pointer to a pointer to the object's security descriptor. The security descriptor must be in self-relative format. This structure must be deallocated by the caller.

### -param AutoInheritFlags [in]

Bitmask that controls automatic inheritance of ACEs. Set to the logical OR of one or more of the following bit flags:

| Security Information Flags | Meaning |
| -------------------------- | ------- |
| SEF_DACL_AUTO_INHERIT | If this flag is set, the DACL is treated as an auto-inherit DACL and is processed as described in the following Remarks section. This bit is ignored if DACL_SECURITY_INFORMATION is not set in the **SecurityInformation** parameter.|
| SEF_SACL_AUTO_INHERIT | If this flag is set, the SACL is treated as an auto-inherit SACL and is processed as described in the following Remarks section. This bit is ignored if SACL_SECURITY_INFORMATION is not set in the **SecurityInformation** parameter.

### -param PoolType [in]

Specifies the pool type to use when allocating a new security descriptor, which can be one of the following:

* **NonPagedPool**
* **PagedPool**
* **NonPagedPoolCacheAligned**
* **PagedPoolCacheAligned**

Usually, a caller specifies **PagedPool**, or else **NonPagedPool** if the buffer will be accessed at IRQL >= DISPATCH_LEVEL or in an arbitrary thread context.

The **NonPagedPoolMustSucceed** and **NonPagedPoolCacheAlignedMustS** pool types are obsolete and should no longer be used.

### -param GenericMapping [in]

Pointer to a GENERIC_MAPPING structure that specifies the mapping of generic to specific and standard access types for the object being accessed. This mapping structure is expected to be safe to access (that is, captured if necessary) prior to be passed to this routine.

## -returns

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS | The object's security descriptor was successfully modified. |
| STATUS_BAD_DESCRIPTOR_FORMAT | The provided object's security descriptor was not in self-relative format. |
| STATUS_NO_SECURITY_ON_OBJECT | The object does not have a security descriptor. |

## -remarks

If the **AutoInheritFlags** parameter is zero, the effect of calling **SeSetSecurityDescriptorInfoEx** is the same as that of calling **SeSetSecurityDescriptorInfo**.

If **AutoInheritFlags** specifies the SEF_DACL_AUTO_INHERIT bit, **SeSetSecurityDescriptorInfoEx** applies the following rules to the DACL to create the new security descriptor from the current descriptor:

* If the SE_DACL_PROTECTED flag is not set in the control bits of the either the current security descriptor or the input **SecurityDescriptor**, **SeSetSecurityDescriptorInfoEx** constructs the output security descriptor from the inherited ACEs of the current security descriptor and noninherited ACEs of **SecurityDescriptor**. That is, it is impossible to change an inherited ACE by changing the ACL on an object. This behavior preserves the inherited ACEs as they were inherited from the parent container.

* If SE_DACL_PROTECTED is set in the input **SecurityDescriptor**, the current security descriptor is ignored. The output security descriptor is built as a copy of the input **SecurityDescriptor** with any INHERITED_ACE bits turned off.

Ideally an ACL editor should turn off the INHERITED_ACE bits indicating to its caller that the ACEs inherited from the object's parent are now being explicitly set on the object.

* If SE_DACL_PROTECTED is set in the current security descriptor and not in the **SecurityDescriptor**, the current security descriptor is ignored. The output security descriptor is built as a copy of the **SecurityDescriptor**. It is the caller's responsibility to ensure that the correct ACEs have the INHERITED_ACE bit turned on.

If **AutoInheritFlags** specifies the SEF_SACL_AUTO_INHERIT bit, **SeSetSecurityDescriptorInfoEx** applies similar rules to the new SACL.

For more information about access control and ACE inheritance, see the Security section of the Microsoft Windows SDK documentation.

## -see-also

[**ACE**](/windows-hardware/drivers/ifs/ace)

[**ACL**](../wdm/ns-wdm-_acl.md)

[**GENERIC_MAPPING**](../wdm/ns-wdm-_generic_mapping.md)

[**RtlCreateSecurityDescriptor**](../wdm/nf-wdm-rtlcreatesecuritydescriptor.md)

[**RtlCreateSecurityDescriptorRelative**](nf-ntifs-rtlcreatesecuritydescriptorrelative.md)

[**RtlLengthSecurityDescriptor**](../wdm/nf-wdm-rtllengthsecuritydescriptor.md)

[**RtlSetDaclSecurityDescriptor**](../wdm/nf-wdm-rtlsetdaclsecuritydescriptor.md)

[**RtlSetOwnerSecurityDescriptor**](nf-ntifs-rtlsetownersecuritydescriptor.md)

[**RtlValidSecurityDescriptor**](../wdm/nf-wdm-rtlvalidsecuritydescriptor.md)

[**SECURITY_DESCRIPTOR**](ns-ntifs-_security_descriptor.md)

[**SECURITY_INFORMATION**](/windows-hardware/drivers/ifs/security-information)

[**SeQuerySecurityDescriptorInfo**](nf-ntifs-sequerysecuritydescriptorinfo.md)

[**SeSetSecurityDescriptorInfo**](nf-ntifs-sesetsecuritydescriptorinfo.md)
