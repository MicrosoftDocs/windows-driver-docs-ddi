---
UID: NF:ntifs.RtlAddAccessAllowedAceEx
title: RtlAddAccessAllowedAceEx function (ntifs.h)
description: Learn more about the RtlAddAccessAllowedAceEx function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["RtlAddAccessAllowedAceEx function"]
ms.keywords: RtlAddAccessAllowedAceEx, RtlAddAccessAllowedAceEx routine [Installable File System Drivers], ifsk.rtladdaccessallowedaceex, ntifs/RtlAddAccessAllowedAceEx, rtlref_c28640a5-62e2-462a-9c30-b59faedc8386.xml
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlAddAccessAllowedAceEx
 - ntifs/RtlAddAccessAllowedAceEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlAddAccessAllowedAceEx
---

# RtlAddAccessAllowedAceEx function

## -description

The **RtlAddAccessAllowedAceEx** routine adds an access-allowed access control entry ([**ACE**](/windows-hardware/drivers/ifs/ace)
) with inheritance ACE flags to an access control list ([**ACL**](../wdm/ns-wdm-_acl.md)). The access is granted to the specified security identifier ([**SID**](ns-ntifs-_sid.md)).

## -parameters

### -param Acl [in, out]

A pointer to a caller-allocated buffer that contains the ACL to be modified. **RtlAddAccessAllowedAceEx** adds an access-allowed ACE to the end of this ACL. The ACE is in the form of an [**ACCESS_ALLOWED_ACE**](ns-ntifs-_access_allowed_ace.md) structure.

### -param AceRevision [in]

ACL revision level of the ACE to be added. This value can be ACL_REVISION or ACL_REVISION_DS. It must be ACL_REVISION_DS if the ACL contains an object-specific ACE.

### -param AceFlags [in]

Bitmask specifying the inherit flags of the ACE to be added.

### -param AccessMask [in]

A bitmask of one or more [**ACCESS_MASK**](/windows-hardware/drivers/kernel/access-mask) flags that specify the access rights to be granted to the specified SID. For more information, see the description of the **DesiredAccess** parameter of [**ZwCreateFile**](nf-ntifs-ntcreatefile.md).

### -param Sid [in]

A pointer to the SID structure that represents a user, group, or logon account that is being granted access.

## -returns

**RtlAddAccessAllowedAceEx** can return one of the following values:

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS    | The ACE was successfully added. |
| STATUS_ALLOTTED_SPACE_EXCEEDED | A new ACE does not fit into the ACL. A larger ACL buffer is required. For more information about how to calculate the size of an ACL, see [**RtlCreateAcl**](nf-ntifs-rtlcreateacl.md). |
| STATUS_INVALID_ACL | The specified ACL is not correctly formed. |
| STATUS_INVALID_PARAMETER       | The AceFlags parameter was invalid. |
| STATUS_INVALID_SID             | The specified SID structure is not structurally valid. |
| STATUS_REVISION_MISMATCH       | The specified **AceRevision** is not known or is not compatible with that of the ACL. |

## -remarks

Unlike [**RtlAddAccessAllowedAce**](nf-ntifs-rtladdaccessallowedace.md), this routine sets the inheritance ACE flags.  

For more information about security and access control, see [Windows security model for driver developers](/windows-hardware/drivers/driversecurity/windows-security-model) and the documentation on these topics in the Windows SDK, such as:

* [Access Control Lists](/windows/win32/secauthz/access-control-lists)

* [Creating or Modifying an ACL](/windows/win32/secauthz/creating-or-modifying-an-acl)

* [Getting Information from an ACL](/windows/win32/secauthz/getting-information-from-an-acl)

## -see-also

[**ACCESS_ALLOWED_ACE**](ns-ntifs-_access_allowed_ace.md)

[**ACCESS_MASK**](/windows-hardware/drivers/kernel/access-mask)

[**ACE**](/windows-hardware/drivers/ifs/ace)

[**ACL**](../wdm/ns-wdm-_acl.md)

[**RtlCreateAcl**](nf-ntifs-rtlcreateacl.md)

[**RtlCreateSecurityDescriptor**](../wdm/nf-wdm-rtlcreatesecuritydescriptor.md)

[**RtlCreateSecurityDescriptorRelative**](nf-ntifs-rtlcreatesecuritydescriptorrelative.md)

[**RtlLengthSecurityDescriptor**](../wdm/nf-wdm-rtllengthsecuritydescriptor.md)

[**RtlSetDaclSecurityDescriptor**](../wdm/nf-wdm-rtlsetdaclsecuritydescriptor.md)

[**RtlSetOwnerSecurityDescriptor**](nf-ntifs-rtlsetownersecuritydescriptor.md)

[**RtlValidSecurityDescriptor**](../wdm/nf-wdm-rtlvalidsecuritydescriptor.md)

[**SID**](ns-ntifs-_sid.md)

[**SeAssignSecurity**](../wdm/nf-wdm-seassignsecurity.md)

[**ZwCreateFile**](nf-ntifs-ntcreatefile.md)
