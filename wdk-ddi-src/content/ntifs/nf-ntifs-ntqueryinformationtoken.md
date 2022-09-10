---
UID: NF:ntifs.NtQueryInformationToken
title: NtQueryInformationToken function (ntifs.h)
description: The NtQueryInformationToken routine retrieves a specified type of information about an access token.
old-location: kernel\zwqueryinformationtoken.htm
tech.root: kernel
ms.date: 07/26/2022
keywords: ["NtQueryInformationToken function"]
ms.keywords: NtQueryInformationToken, ZwQueryInformationToken, ZwQueryInformationToken routine [Kernel-Mode Driver Architecture], k111_2f945a17-f3b4-423a-90fa-6f02d240d42d.xml, kernel.zwqueryinformationtoken, ntifs/NtQueryInformationToken, ntifs/ZwQueryInformationToken
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP
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
 - NtQueryInformationToken
 - ntifs/NtQueryInformationToken
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - NtQueryInformationToken
---

# NtQueryInformationToken function

## -description

The **NtQueryInformationToken** routine retrieves a specified type of information about an access token. The calling process must have appropriate access rights to obtain the information.

## -parameters

### -param TokenHandle [in]

Handle for an access token from which information is to be retrieved. If **TokenInformationClass** is set to **TokenSource**, the handle must have TOKEN_QUERY_SOURCE access. For all other **TokenInformationClass** values, the handle must have TOKEN_QUERY access. For more information about access rights for access-token objects, see the Security section of the Windows SDK documentation.

### -param TokenInformationClass [in]

A value from the [**TOKEN_INFORMATION_CLASS**](ne-ntifs-_token_information_class.md) enumerated type identifying the type of information to be retrieved. The possible values for this parameter are listed in the **TokenInformationClass** Value column of the table shown in the description of the **TokenInformation** parameter.

### -param TokenInformation [out]

Pointer to a caller-allocated buffer that receives the requested information about the token. The structure put into this buffer depends upon the value of **TokenInformationClass**, as shown in the following table. All structures must be aligned on a 32-bit boundary.

| TokenInformationClass value | Effect on TokenInformation buffer |
| --------------------------- | --------------------------------- |
| **TokenDefaultDacl**        | The buffer receives a [**TOKEN_DEFAULT_DACL**](ns-ntifs-_token_default_dacl.md) structure containing the default [**DACL**](../wdm/ns-wdm-_acl.md) for newly created objects. |
| **TokenGroups**             | The buffer receives a [**TOKEN_GROUPS**](ns-ntifs-_token_groups.md) structure containing the group accounts associated with the token. |
| **TokenImpersonationLevel** | The buffer receives a [**SECURITY_IMPERSONATION_LEVEL**](../wdm/ne-wdm-_security_impersonation_level.md) value indicating the impersonation level of the token. If the access token is not an impersonation token, the call to **NtQueryInformationToken** fails. |
| **TokenOwner**              | The buffer receives a [**TOKEN_OWNER**](ns-ntifs-_token_owner.md) structure containing the default owner [**SID**](ns-ntifs-_sid.md) for newly created objects. |
| **TokenPrimaryGroup**       | The buffer receives a [**TOKEN_PRIMARY_GROUP**](ns-ntifs-_token_primary_group.md) structure containing the default primary group SID for newly created objects. |
| **TokenPrivileges**         | The buffer receives a [**TOKEN_PRIVILEGES**](ns-ntifs-_token_privileges.md) structure containing the token's privileges. |
| **TokenSessionId**          | The buffer receives a 32-bit value specifying the Terminal Services session identifier associated with the token. If the token is associated with the Terminal Server console session, the session identifier is zero. A nonzero session identifier indicates a Terminal Services client session. In a non-Terminal Services environment, the session identifier is zero. |
| **TokenSource**             | The buffer receives a [**TOKEN_SOURCE**](ns-ntifs-_token_source.md) structure containing the source of the token. TOKEN_QUERY_SOURCE access is needed to retrieve this information. |
| **TokenStatistics**         | The buffer receives a [**TOKEN_STATISTICS**](ns-ntifs-_token_statistics.md) structure containing various token statistics. |
| **TokenType**               | The buffer receives a [**TOKEN_TYPE**](ne-ntifs-_token_type.md) value indicating whether the token is a primary or impersonation token. |
| **TokenUser**               | The buffer receives a [**TOKEN_USER**](ns-ntifs-_token_user.md) structure containing the token's user account. |

### -param TokenInformationLength [in]

Length, in bytes, of the caller-allocated **TokenInformation** buffer.

### -param ReturnLength [out]

Pointer to a caller-allocated variable that receives the actual length, in bytes, of the information returned in the **TokenInformation** buffer. If either of the following conditions is true, no data is returned in the **TokenInformation** buffer:

* The size of the requested token information structure is greater than **TokenInformationLength**. In this case, **ReturnLength** receives the actual number of bytes needed to store the requested information.

* The value of **TokenInformationClass** is **TokenDefaultDacl**, and there is no default DACL established for the token. In this case, **ReturnLength** receives zero.

**ReturnLength** cannot be **NULL**. See Remarks for further information.

## -returns

**NtQueryInformationToken** returns STATUS_SUCCESS or an appropriate error status. Possible error status codes include the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_ACCESS_DENIED           | **TokenHandle** did not have the required access. |
| STATUS_BUFFER_TOO_SMALL        | The size of the requested token information structure is greater than **TokenInformationLength**. The number of bytes required is returned in **ReturnLength**. |
| STATUS_ACCESS_VIOLATION        | **ReturnLength** was NULL or was not writable in order to receive the actual length of the information pointed by **TokenInformation**. |
| STATUS_INVALID_HANDLE          | **TokenHandle** was not a valid handle. |
| STATUS_INVALID_INFO_CLASS      | **TokenInformationClass** was not a valid token information class. |
| STATUS_OBJECT_TYPE_MISMATCH    | **TokenHandle** was not a token handle. |

## -remarks

The **NtQueryInformationToken** routine can be used by a file system or file system filter driver to determine the [**SID**](ns-ntifs-_sid.md) of the caller that initiated the request during [**IRP_MJ_CREATE**](/windows-hardware/drivers/ifs/irp-mj-create) processing. If **TokenUser** is specified for the **TokenInformationClass** parameter passed to **NtQueryInformationToken**, a [**TOKEN_USER**](ns-ntifs-_token_user.md) structure is returned in the buffer pointed to by the **TokenInformation** parameter. This returned buffer contains an [**SID_AND_ATTRIBUTES**](ns-ntifs-_sid_and_attributes.md) structure with the user **SID**.

Due to the nature of token's properties (such as token user, token primary group, privileges, etc, where their contents can vary on each token), **ReturnLength** is not optional; that is, it cannot be NULL. This is because
SID is a variable-length structure whereas a specific privilege can exist in a token but not in another (the privilege count can be different for each token). It's the caller's responsibility to first query the necessary
required length size in order to allocate memory to accommodate the requested token information before doing the actual query. That said, it is also the caller's responsibility to provide a valid **ReturnLength** variable that is writable and not NULL. On a NULL case scenario, the function raises an access violation exception.

For more information about security and access control, see the documentation on these topics in the Windows SDK.

> [!NOTE]
> If the call to the **NtQueryInformationToken** function occurs in user mode, you should use the name "**NtQueryInformationToken**" instead of "**ZwQueryInformationToken**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**ACL**](../wdm/ns-wdm-_acl.md)

[**IRP_MJ_CREATE**](/windows-hardware/drivers/ifs/irp-mj-create)

[**SECURITY_IMPERSONATION_LEVEL**](../wdm/ne-wdm-_security_impersonation_level.md)

[**SID**](ns-ntifs-_sid.md)

[**SID_AND_ATTRIBUTES**](ns-ntifs-_sid_and_attributes.md)

[**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md)

[**TOKEN_DEFAULT_DACL**](ns-ntifs-_token_default_dacl.md)

[**TOKEN_GROUPS**](ns-ntifs-_token_groups.md)

[**TOKEN_INFORMATION_CLASS**](ne-ntifs-_token_information_class.md)

[**TOKEN_OWNER**](ns-ntifs-_token_owner.md)

[**TOKEN_PRIMARY_GROUP**](ns-ntifs-_token_primary_group.md)

[**TOKEN_PRIVILEGES**](ns-ntifs-_token_privileges.md)

[**TOKEN_SOURCE**](ns-ntifs-_token_source.md)

[**TOKEN_STATISTICS**](ns-ntifs-_token_statistics.md)

[**TOKEN_TYPE**](ne-ntifs-_token_type.md)

[**TOKEN_USER**](ns-ntifs-_token_user.md)

[**ZwSetInformationToken**](nf-ntifs-zwsetinformationtoken.md)
