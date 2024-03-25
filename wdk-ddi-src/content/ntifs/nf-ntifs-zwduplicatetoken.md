---
UID: NF:ntifs.ZwDuplicateToken
title: ZwDuplicateToken function (ntifs.h)
description: Learn more about the ZwDuplicateToken function.
tech.root: kernel
ms.date: 09/27/2023
keywords: ["ZwDuplicateToken function"]
ms.keywords: NtDuplicateToken, ZwDuplicateToken, ZwDuplicateToken function [Kernel-Mode Driver Architecture], k111_5c46bc83-ec51-45f5-a3fc-e199f91d58ce.xml, kernel.zwduplicatetoken, ntifs/NtDuplicateToken, ntifs/ZwDuplicateToken
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
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
 - ZwDuplicateToken
 - ntifs/ZwDuplicateToken
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwDuplicateToken
---

# ZwDuplicateToken function

## -description

The **ZwDuplicateToken** function creates a handle to a new [access token](/windows/win32/secgloss/a-gly) that duplicates an existing token. This function can create either a primary token or an impersonation token.

## -parameters

### -param ExistingTokenHandle [in]

A handle to an existing access token that was opened with the TOKEN_DUPLICATE access right. This parameter is required and cannot be NULL.

### -param DesiredAccess [in]

Bitmask that specifies the requested access rights for the new token. **ZwDuplicateToken** compares the requested access rights with the existing token's discretionary access control list (DACL) to determine which rights are granted or denied to the new token. To request the same access rights as the existing token, specify zero. To request all access rights that are valid for the caller, specify MAXIMUM_ALLOWED. This parameter is optional and can either be zero, MAXIMUM_ALLOWED, or a bitwise OR combination of one or more of the following values:

| Value | Meaning |
| ----- | ------- |
| DELETE | Required to delete the object. |
| READ_CONTROL | Required to read the DACL and ownership information for the object. For access to the system access control list (SACL), see ACCESS_SYSTEM_SECURITY later in this table. |
| WRITE_DAC | Required to change the DACL information for the object. |
| WRITE_OWNER | Required to change the ownership information in the object's security descriptor ([**SECURITY_DESCRIPTOR**](ns-ntifs-_security_descriptor.md)). |
| ACCESS_SYSTEM_SECURITY | Required to get or set the SACL in an object's ACL. The operating system grants this right to the new token only if the SE_SECURITY_NAME privilege is enabled in the access token of the calling thread. |
| STANDARD_RIGHTS_READ | Currently defined to equal READ_CONTROL. |
| STANDARD_RIGHTS_WRITE | Currently defined to equal READ_CONTROL. |
| STANDARD_RIGHTS_EXECUTE | Currently defined to equal READ_CONTROL. |
| STANDARD_RIGHTS_REQUIRED | Combines DELETE, READ_CONTROL, WRITE_DAC, and WRITE_OWNER access. |
| STANDARD_RIGHTS_ALL | Combines DELETE, READ_CONTROL, WRITE_DAC, WRITE_OWNER, and SYNCHRONIZE access. However, the SYNCHRONIZE value is not applicable to token objects. Thus, STANDARD_RIGHTS_ALL has a  functionally equivalent to STANDARD_RIGHTS_REQUIRED. |
| TOKEN_ADJUST_DEFAULT | Required to change the default owner, primary group, or DACL of an access token. |
| TOKEN_ADJUST_GROUPS | Required to adjust the attributes of the groups in an access token. |
| TOKEN_ADJUST_PRIVILEGES | Required to enable or disable the privileges in an access token. |
| TOKEN_ADJUST_SESSIONID | Required to adjust the session ID (SID) of an access token. The operating system grants this right to the new token only if the SE_TCB_NAME privilege is enabled in the access token of the calling thread. |
| TOKEN_ASSIGN_PRIMARY | Required to attach a primary token to a process. The operating system grants this right to the new token only if the SE_ASSIGNPRIMARYTOKEN_NAME privilege is enabled in the access token of the calling thread. |
| TOKEN_DUPLICATE | Required to duplicate an access token. Note that the given **ExistingTokenHandle** token must contain this right in order to successfully use this routine. |
| TOKEN_EXECUTE | Combines STANDARD_RIGHTS_EXECUTE and TOKEN_IMPERSONATE. |
| TOKEN_IMPERSONATE | Required to attach an impersonation access token to a process. |
| TOKEN_QUERY | Required to query an access token. |
| TOKEN_QUERY_SOURCE | Required to query the source of an access token. |
| TOKEN_READ | Combines STANDARD_RIGHTS_READ and TOKEN_QUERY. |
| TOKEN_WRITE | Combines STANDARD_RIGHTS_WRITE, TOKEN_ADJUST_PRIVILEGES, TOKEN_ADJUST_GROUPS, and TOKEN_ADJUST_DEFAULT. |
| TOKEN_ALL_ACCESS | Combines all possible token access permissions for a token.

For additional information, see [Access Rights for Access-Token Objects](/windows/win32/secauthz/access-rights-for-access-token-objects) in the Windows SDK. Note that access tokens do not support the SYNCHRONIZE right.

### -param ObjectAttributes [in]

Pointer to an [**OBJECT_ATTRIBUTES**](/windows/win32/api/ntdef/ns-ntdef-_object_attributes) structure that describes the requested properties for the new token. The **ObjectAttributes** parameter is optional and can be NULL. If the **ObjectAttributes** parameter is NULL or if the **SecurityDescriptor** member of the structure pointed to by the **ObjectAttributes** parameter is NULL, the new token receives a default security descriptor and the new token handle cannot be inherited. In that case, this default security descriptor is created from the user group, primary group, and DACL information that is stored in the caller's token.

When the **TokenType** parameter is set to **TokenImpersonation**:

* The **ObjectAttributes** parameter may be used to specify the impersonation level of the new token. This can be accomplished by setting **ObjectAttributes**->SecurityQualityOfService.ImpersonationLevel to an appropriate [**SECURITY_IMPERSONATION_LEVEL**](../wdm/ne-wdm-_security_impersonation_level.md) enumeration value. For more information, see [**SECURITY_QUALITY_OF_SERVICE**](/windows/win32/api/winnt/ns-winnt-security_quality_of_service).

* If the existing token is an impersonation token and the **ObjectAttributes** parameter provides no impersonation information, the new token's impersonation level is set to the existing token's impersonation level.

* If the existing token is a primary token and no impersonation level information is provided, the new impersonation token will have a [**SECURITY_IMPERSONATION_LEVEL**](../wdm/ne-wdm-_security_impersonation_level.md) impersonation level.

### -param EffectiveOnly [in]

A Boolean value that indicates whether the entire existing token should be duplicated into the new token or just the effective (currently enabled) part of the token. If set to TRUE, only the currently enabled parts of the source token will be duplicated. If set to FALSE, the entire existing token will be duplicated. This provides a means for a caller of a protected subsystem to limit which optional groups and privileges are made available to the protected subsystem. For example, if **EffectiveOnly** is TRUE, the caller could duplicate a token but remove the Administrators group and the SeTcbPrivilege right. The resulting token could then be passed to a child process ([**CreateProcessAsUser**](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessasusera)), which would restrict what the child process can do. This parameter is required.

### -param TokenType [in]

Specifies one of the following values from the [**TOKEN_TYPE**](ne-ntifs-_token_type.md) enumeration.

| Value | Meaning |
| ----- | ------- |
| **TokenPrimary**       | The new token is a primary token. If the existing token is an impersonation token, the existing impersonation token must have an impersonation level (as provided by the **ObjectAttributes** parameter) of **SecurityImpersonation** or **SecurityDelegation**. Otherwise, **ZwDuplicateToken** returns STATUS_BAD_IMPERSONATION_LEVEL is returned.
| **TokenImpersonation** | The new token is an impersonation token. If the existing token is an impersonation token, the requested impersonation level (as provided by the **ObjectAttributes** parameter) of the new token must not be greater than the impersonation level of the existing token. Otherwise, **ZwDuplicateToken** returns STATUS_BAD_IMPERSONATION_LEVEL.

The **TokenType** parameter is required and cannot be NULL.

### -param NewTokenHandle [out]

A pointer to a caller-allocated variable, of type HANDLE, that receives a handle to the new token. This parameter is required and cannot be NULL.

## -returns

**ZwDuplicateToken** returns STATUS_SUCCESS if the call is successfull. Possible error return codes include the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_ACCESS_VIOLATION | A memory access violation occurred. For example, if the previous mode was user-mode and invalid user-mode memory was provided, **ZwDuplicateToken** returns STATUS_ACCESS_VIOLATION.  |
| STATUS_INSUFFICIENT_RESOURCES | Sufficient memory could not be allocated to duplicate the new token.  |
| STATUS_INVALID_PARAMETER | An invalid parameter was detected.  |
| STATUS_BAD_IMPERSONATION_LEVEL | The requested impersonation level for the new token is greater than the impersonation level of the existing token.  |
| STATUS_ACCESS_DENIED | **ZwDuplicateToken** returns STATUS_ACCESS_DENIED if it couldn't access **ExistingTokenHandle**. This would occur if the existing token does not have the TOKEN_DUPLICATE access right.  |
| STATUS_INVALID_HANDLE | **ZwDuplicateToken** returns STATUS_INVALID_HANDLE if **ExistingTokenHandle** refers to an invalid handle. |

## -remarks

If no impersonation level information was provided by the **ObjectAttributes** parameter, the existing token's impersonation level will be used for the new token.

With regard to the structure pointed to by the optional **ObjectAttributes** parameter, the **SecurityQualityOfService** member of [**OBJECT_ATTRIBUTES**](/windows/win32/api/ntdef/ns-ntdef-_object_attributes) points to a structure of type **SECURITY_QUALITY_OF_SERVICE**. See [**SECURITY_QUALITY_OF_SERVICE**](/windows/win32/api/winnt/ns-winnt-security_quality_of_service) for information on the members of this structure.

The **SecurityQualityOfService** member must be set *after* calling the [**InitializeObjectAttributes**](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes) macro because **InitializeObjectAttributes** currently sets **SecurityQualityOfService** to NULL.

For information on the user-mode analog of **ZwDuplicateToken**, see [**DuplicateTokenEx**](/windows/win32/api/securitybaseapi/nf-securitybaseapi-duplicatetokenex).

When you have finished using the new token, call the [**ZwClose**](nf-ntifs-ntclose.md) function to close the token handle.

If the call to the **ZwDuplicateToken** function occurs in user mode, you should use the name "**NtDuplicateToken**" instead of "**ZwDuplicateToken**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**ACCESS_MASK**](/windows-hardware/drivers/kernel/access-mask)

[**InitializeObjectAttributes**](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes)

[**OBJECT_ATTRIBUTES**](/windows/win32/api/ntdef/ns-ntdef-_object_attributes)

[**SECURITY_IMPERSONATION_LEVEL**](../wdm/ne-wdm-_security_impersonation_level.md)
