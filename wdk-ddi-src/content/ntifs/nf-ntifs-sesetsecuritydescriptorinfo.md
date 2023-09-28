---
UID: NF:ntifs.SeSetSecurityDescriptorInfo
title: SeSetSecurityDescriptorInfo function (ntifs.h)
description: Learn more about the SeSetSecurityDescriptorInfo function.
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["SeSetSecurityDescriptorInfo function"]
ms.keywords: SeSetSecurityDescriptorInfo, SeSetSecurityDescriptorInfo routine [Installable File System Drivers], ifsk.sesetsecuritydescriptorinfo, ntifs/SeSetSecurityDescriptorInfo, seref_061b8609-a537-4ccb-aa60-50a46b08e97f.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - SeSetSecurityDescriptorInfo
 - ntifs/SeSetSecurityDescriptorInfo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - SeSetSecurityDescriptorInfo
---

# SeSetSecurityDescriptorInfo function

## -description

The **SeSetSecurityDescriptorInfo** routine sets an object's security descriptor.

## -parameters

### -param Object [in, optional]

Pointer to the object whose security descriptor is to be set. This is used to update security quota information.

### -param SecurityInformation [in]

Pointer to a bitmask specifying which security information is to be applied to the object. Can be a combination of one or more of the following values.

| Value | Meaning |
| ----- | ------- |
| DACL_SECURITY_INFORMATION | Indicates the discretionary access control list (DACL) of the object is being set. Requires WRITE_DAC access. |
| GROUP_SECURITY_INFORMATION | Indicates the primary group identifier of the object is being set. Requires WRITE_OWNER access. |
| OWNER_SECURITY_INFORMATION | Indicates the owner identifier of the object is being set. Requires WRITE_OWNER access. |
| SACL_SECURITY_INFORMATION | Indicates the system ACL (SACL) of the object is being set. Requires ACCESS_SYSTEM_SECURITY access. |

### -param ModificationDescriptor

The input security descriptor to be applied to the object. The caller of this routine is expected to probe and capture the passed security descriptor before calling **SeSetSecurityDescriptorInfo**, and to release it afterward.

### -param ObjectsSecurityDescriptor [in, out]

Pointer to a pointer to the object's security descriptor. The security descriptor must be in self-relative format. The caller is responsible for freeing this structure when it is no longer needed.

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
| STATUS_NO_SECURITY_ON_OBJECT | The object does not have a security descriptor.

## -remarks

**SeSetSecurityDescriptorInfo** modifies an object's existing security descriptor. If the object does not have a security descriptor, the call to **SeSetSecurityDescriptorInfo** will fail.

To specify whether the object supports automatic inheritance of access control entries (ACE), use **SeSetSecurityDescriptorInfoEx**.

A security descriptor can be in absolute or self-relative form. In self-relative form, all members of the structure are located contiguously in memory. In absolute form, the structure only contains pointers to the members.

For more information about security and access control, see [Windows security model for driver developers](/windows-hardware/drivers/driversecurity/windows-security-model) and the documentation on these topics in the Windows SDK.

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

[**SeSetAccessStateGenericMapping**](nf-ntifs-sesetaccessstategenericmapping.md)

[**SeSetSecurityDescriptorInfoEx**](nf-ntifs-sesetsecuritydescriptorinfoex.md)
