---
UID: NF:ntifs.SePrivilegeCheck
title: SePrivilegeCheck function (ntifs.h)
description: The SePrivilegeCheck routine determines whether a specified set of privileges is enabled in the subject's access token.
old-location: ifsk\seprivilegecheck.htm
tech.root: ifsk
ms.date: 06/21/2021
keywords: ["SePrivilegeCheck function"]
ms.keywords: SePrivilegeCheck, SePrivilegeCheck routine [Installable File System Drivers], ifsk.seprivilegecheck, ntifs/SePrivilegeCheck, seref_45aa3a8c-26b9-4bb9-968a-5f7d4a12ca3a.xml
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
 - SePrivilegeCheck
 - ntifs/SePrivilegeCheck
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - SePrivilegeCheck
---

# SePrivilegeCheck function

## -description

The **SePrivilegeCheck** routine determines whether a specified set of privileges is enabled in the subject's access token.

## -parameters

### -param RequiredPrivileges [in, out]

Pointer to a PRIVILEGE_SET structure. The **Privilege** member of this structure is an array of LUID_AND_ATTRIBUTES structures. Before calling **SePrivilegeCheck**, use the **Privilege** array to indicate the set of privileges to check. Set the **Control** member to PRIVILEGE_SET_ALL_NECESSARY if all of the privileges must be enabled; or set it to zero if it is sufficient that any one of the privileges be enabled.

When **SePrivilegeCheck** returns, the **Attributes** member of each LUID_AND_ATTRIBUTES structure is set to SE_PRIVILEGE_USED_FOR_ACCESS if the corresponding privilege is enabled.

### -param SubjectSecurityContext [in]

Pointer to the subject's captured security context.

### -param AccessMode [in]

The access mode to use for the privilege check. Either **UserMode** or **KernelMode**. If **AccessMode** is set to **KernelMode**, then all privileges are marked as being possessed by the subject, and **SePrivilegeCheck** returns **TRUE**.

## -returns

**SePrivilegeCheck** returns **TRUE** if all specified privileges are held by the subject, **FALSE** otherwise.

## -remarks

An access token contains a list of the privileges held by the account associated with the token. These privileges can be enabled or disabled; most are disabled by default. **SePrivilegeCheck** checks only for enabled privileges. To get a list of all the enabled and disabled privileges held by an access token, call [**SeQueryInformationToken**](./nf-ntifs-sequeryinformationtoken.md).

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.

## -see-also

[**LUID_AND_ATTRIBUTES**](../wdm/ns-wdm-_luid_and_attributes.md)

[**PRIVILEGE_SET**](/previous-versions/windows/hardware/drivers/ff551860(v=vs.85))

[**SECURITY_SUBJECT_CONTEXT**](/windows-hardware/drivers/kernel/eprocess)

[**SeAccessCheck**](../wdm/nf-wdm-seaccesscheck.md)

[**SeAppendPrivileges**](./nf-ntifs-seappendprivileges.md)

[**SeFreePrivileges**](./nf-ntifs-sefreeprivileges.md)

[**SeQueryInformationToken**](./nf-ntifs-sequeryinformationtoken.md)

[**SeSinglePrivilegeCheck**](../ntddk/nf-ntddk-sesingleprivilegecheck.md)
