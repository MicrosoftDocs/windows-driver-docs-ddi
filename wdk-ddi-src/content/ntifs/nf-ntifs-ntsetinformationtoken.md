---
UID: NF:ntifs.NtSetInformationToken
title: NtSetInformationToken function (ntifs.h)
description: The NtSetInformationToken routine modifies information in a specified token. The calling process must have access rights to set the information.
old-location: kernel\zwsetinformationtoken.htm
tech.root: kernel
ms.date: 07/26/2022
keywords: ["NtSetInformationToken function"]
ms.keywords: NtSetInformationToken, ZwSetInformationToken, ZwSetInformationToken routine [Kernel-Mode Driver Architecture], k111_1122461b-dab8-4a40-8f05-db62ca25763b.xml, kernel.zwsetinformationtoken, ntifs/NtSetInformationToken, ntifs/ZwSetInformationToken
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 7
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
 - NtSetInformationToken
 - ntifs/NtSetInformationToken
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - NtSetInformationToken
---

# NtSetInformationToken function

## -description

The **NtSetInformationToken** routine modifies information in a specified token. The calling process must have appropriate access rights to set the information.

## -parameters

### -param TokenHandle [in]

Handle for an access token in which information is to be modified.

### -param TokenInformationClass [in]

A value from the [**TOKEN_INFORMATION_CLASS**](ne-ntifs-_token_information_class.md) enumerated type identifying the type of information to be modified. The possible values for this parameter are listed in the **TokenInformationClass** Value column of the table shown in the description of the **TokenInformation** parameter.

### -param TokenInformation [in]

Pointer to a caller-supplied buffer containing the information to be modified in the token. The structure of the information in this buffer depends upon the value of **TokenInformationClass**, as shown in the following table. All structures must be aligned on a 32-bit boundary.

| TokenInformationClass value | Effect on TokenInformation buffer |
| --------------------------- | --------------------------------- |
| **TokenDefaultDacl**    | The buffer contains a [**TOKEN_DEFAULT_DACL**](ns-ntifs-_token_default_dacl.md) structure specifying the default [**DACL**](../wdm/ns-wdm-_acl.md) for newly created objects. TOKEN_ADJUST_DEFAULT access is required to set this information. The buffer contents are not validated for structural correctness or consistency. |
| **TokenGroups**         | Not a valid information class. This information is read-only. |
| **TokenOwner**          | The buffer contains a [**TOKEN_OWNER**](ns-ntifs-_token_owner.md) structure specifying the default owner [**SID**](ns-ntifs-_sid.md) for newly created objects. TOKEN_ADJUST_DEFAULT access is required to set this information. The owner values that may be specified are restricted to the user and group IDs with an attribute indicating they can be assigned as the owner of objects. |
| **TokenPrimaryGroup**   | The buffer contains a [**TOKEN_PRIMARY_GROUP**](ns-ntifs-_token_primary_group.md) structure specifying the default primary group **SID** for newly created objects. TOKEN_ADJUST_DEFAULT access is required to set this information. Must be one of the group IDs already in the token. |
| **TokenPrivileges**     | Not a valid information class. This information is read-only. |
| **TokenSource**         | Not a valid information class. This information is read-only. |
| **TokenStatistics**     | Not a valid information class. This information is read-only. |
| **TokenUser**           | Not a valid information class. This information is read-only. |

### -param TokenInformationLength [in]

Size, in bytes, of the structure passed in the **TokenInformation** buffer. Must be greater than or equal to the minimum value given in the following table.

| TokenInformationClass value | Minimum TokenInformationLength |
| --------------------------- | ------------------------------ |
| **TokenDefaultDacl**  | **sizeof**(**TOKEN_DEFAULT_DACL**) |
| **TokenOwner**        | **sizeof**(**TOKEN_OWNER**) |
| **TokenPrimaryGroup** | **sizeof**(**TOKEN_PRIMARY_GROUP**) |

## -returns

**NtSetInformationToken** returns STATUS_SUCCESS or an appropriate error status. Possible error status codes include the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_ACCESS_DENIED           | **TokenHandle** did not have the required access. |
| STATUS_ALLOTTED_SPACE_EXCEEDED | The space allotted for storage of the default discretionary access control and the primary group ID is not large enough to accept the new value of one of these fields. |
| STATUS_INFO_LENGTH_MISMATCH | The value of **TokenInformationLength** was less than the required minimum. |
| STATUS_INSUFFICIENT_RESOURCES | The specified default owner's security information could not be captured. |
| STATUS_INVALID_HANDLE          | **TokenHandle** was not a valid handle. |
| STATUS_INVALID_INFO_CLASS      | **TokenInformationClass** was not a valid token information class. |
| STATUS_INVALID_OWNER | The caller cannot set the specified ID to be an owner (or default owner) of an object. |
| STATUS_INVALID_PRIMARY_GROUP | The caller cannot set the specified ID to be the primary group of an object. |
| STATUS_INVALID_SID | The specified default owner's security information was not valid. |
| STATUS_OBJECT_TYPE_MISMATCH    | **TokenHandle** was not a token handle. |

## -remarks

For more information about security and access control, see the documentation on these topics in the Windows SDK.

> [!NOTE]
> If the call to the **NtSetInformationToken** function occurs in kernel mode, you should use the name "[**ZwSetInformationToken**](nf-ntifs-zwsetinformationtoken.md)" instead of "**NtSetInformationToken**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**NtQueryInformationToken**](nf-ntifs-ntqueryinformationtoken.md)

[**PsDereferenceImpersonationToken**](nf-ntifs-psdereferenceimpersonationtoken.md)

[**PsDereferencePrimaryToken**](nf-ntifs-psdereferenceprimarytoken.md)

[**SECURITY_IMPERSONATION_LEVEL**](../wdm/ne-wdm-_security_impersonation_level.md)

[**SID**](ns-ntifs-_sid.md)

[**SeQueryAuthenticationIdToken**](nf-ntifs-sequeryauthenticationidtoken.md)

[**SeQuerySubjectContextToken**](nf-ntifs-sequerysubjectcontexttoken.md)

[**SeTokenIsAdmin**](nf-ntifs-setokenisadmin.md)

[**SeTokenIsRestricted**](nf-ntifs-setokenisrestricted.md)

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

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)
