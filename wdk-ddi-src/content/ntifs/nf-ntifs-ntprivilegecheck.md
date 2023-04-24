---
UID: NF:ntifs.NtPrivilegeCheck
tech.root: kernel
title: NtPrivilegeCheck function (ntifs.h)
ms.date: 10/06/2022
targetos: Windows
description: The NtPrivilegeCheck routine determines whether a specified set of privileges is enabled in the subject's access token.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.header: ntifs.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - ntifs.h
api_name:
 - NtPrivilegeCheck
f1_keywords:
 - NtPrivilegeCheck
 - ntifs/NtPrivilegeCheck
dev_langs:
 - c++
ms.custom: engagement-fy23
---

## -description

**NtPrivilegeCheck** is reserved for system use.

## -parameters

### -param ClientToken [in]

A handle to a token object representing a client attempting access. This handle must be obtained from a communication session layer, such as from an LPC Port or Local Named Pipe, to prevent possible security policy violations.

### -param RequiredPrivileges [in, out]

Pointer to a [**PRIVILEGE_SET**](../wdm/ns-wdm-_privilege_set.md) structure. The **Privilege** member of this structure is an array of LUID_AND_ATTRIBUTES structures. Before calling **SePrivilegeCheck**, use the **Privilege** array to indicate the set of privileges to check. Set the **Control** member to PRIVILEGE_SET_ALL_NECESSARY if all of the privileges must be enabled; or set it to zero if it is sufficient that any one of the privileges be enabled.

### -param Result [out]

Receives a boolean flag indicating whether the client has all the specified privileges. A value of TRUE indicates the client has all the specified privileges; otherwise a value of FALSE is returned.

## -returns

**NtPrivilegeCheck** returns STATUS_SUCCESS on successful completion. Otherwise, it returns an error code, such as the following.

| Return code | Description |
| ----------- | ----------- |
| STATUS_PRIVILEGE_NOT_HELD | The caller does not have sufficient privilege to use this privileged system service. |

## -remarks

An access token contains a list of the privileges held by the account associated with the token. These privileges can be enabled or disabled; most are disabled by default. **NtPrivilegeCheck** checks only for enabled privileges. To get a list of all the enabled and disabled privileges held by an access token, call [**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md).

For more information about security and access control, see [Windows security model for driver developers](/windows-hardware/drivers/driversecurity/windows-security-model) and the documentation on these topics in the Windows SDK.

## -see-also

[**LUID_AND_ATTRIBUTES**](../wdm/ns-wdm-_luid_and_attributes.md)

[**PRIVILEGE_SET**](../wdm/ns-wdm-_privilege_set.md)

[**SECURITY_SUBJECT_CONTEXT**](/windows-hardware/drivers/kernel/eprocess#security_subject_context)

[**SeAccessCheck**](../wdm/nf-wdm-seaccesscheck.md)

[**SeAppendPrivileges**](nf-ntifs-seappendprivileges.md)

[**SeFreePrivileges**](nf-ntifs-sefreeprivileges.md)

[**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md)

[**SeSinglePrivilegeCheck**](../ntddk/nf-ntddk-sesingleprivilegecheck.md)
