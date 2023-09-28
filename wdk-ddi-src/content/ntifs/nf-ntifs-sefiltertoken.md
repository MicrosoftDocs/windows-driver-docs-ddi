---
UID: NF:ntifs.SeFilterToken
title: SeFilterToken function (ntifs.h)
description: Learn more about the SeFilterToken function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["SeFilterToken function"]
ms.keywords: SeFilterToken, SeFilterToken routine [Installable File System Drivers], ifsk.sefiltertoken, ntifs/SeFilterToken, seref_33edad21-5cc4-4bd9-86f1-b52c648fc87c.xml
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP
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
req.irql: < DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - SeFilterToken
 - ntifs/SeFilterToken
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - SeFilterToken
---

# SeFilterToken function

## -description

The **SeFilterToken** routine creates a new access token that is a restricted version of an existing access token.

## -parameters

### -param ExistingToken [in]

Pointer to a primary or impersonation token. The token can also be a restricted token. This token must already be open for TOKEN_DUPLICATE access. This pointer can be obtained from an existing token handle by calling [**ObReferenceObjectByHandle**](../wdm/nf-wdm-obreferenceobjectbyhandle.md), specifying TOKEN_DUPLICATE as the **DesiredAccess** type.

### -param Flags [in]

Specifies additional privilege options. This parameter can be zero or a combination of the following values.

 Value | Meaning |
| ----- | ------- |
| DISABLE_MAX_PRIVILEGE | Disables all privileges in the new token except SE_CHANGE_NOTIFY_PRIVILEGE. If this value is specified, the **PrivilegesToDelete** parameter is ignored.  |
| SANDBOX_INERT         | Stores the TOKEN_SANDBOX_INERT flag in the token. |

### -param SidsToDisable [in, optional]

Pointer to a TOKEN_GROUPS structure containing an array of SID_AND_ATTRIBUTES structures that specify the deny-only SIDs in the restricted token. The system uses a deny-only SID to deny access to a securable object. The absence of a deny-only SID does not allow access.

Disabling a SID *turns on* SE_GROUP_USE_FOR_DENY_ONLY and *turns off* SE_GROUP_ENABLED and SE_GROUP_ENABLED_BY_DEFAULT. All other attributes are ignored.

Deny-only attributes apply to any combination of an existing token's SIDs, including the user SID and group SIDs that have the SE_GROUP_MANDATORY attribute. To get the SIDs associated with the existing token, call [**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md) with the TokenUser and TokenGroups flags. **SeFilterToken** ignores any SIDs in the array that are not also found in the existing token.

**SeFilterToken** ignores the **Attributes** members of the SID_AND_ATTRIBUTES structures.

This parameter is optional and can be NULL.

### -param PrivilegesToDelete [in, optional]

Pointer to a TOKEN_PRIVILEGES structure containing an array of LUID_AND_ATTRIBUTES structures that specify the privileges to delete in the restricted token.

To get the privileges held by the existing token, call [**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md) with the TokenPrivileges flag. **SeFilterToken** ignores any privileges in the array that are not held by the existing token.

**SeFilterToken** ignores the **Attributes** members of the LUID_AND_ATTRIBUTES structures.

This parameter is optional and can be NULL.

### -param RestrictedSids [in, optional]

Pointer to a TOKEN_GROUPS structure containing an array of SID_AND_ATTRIBUTES structures that specify a list of restricting SIDs for the new token. If the existing token is a restricted token, the list of restricting SIDs for the new token is the intersection of this array and the list of restricting SIDs for the existing token.

The **Attributes** members of the SID_AND_ATTRIBUTES structures must be zero. Restricting SIDs are always enabled for access checks.

This parameter is optional and can be NULL.

### -param FilteredToken

Pointer to a caller-allocated variable that receives the address of the new restricted token. The new token is the same type, primary or impersonation, as the existing token.

## -returns

If one or more of the parameter values were invalid, **SeFilterToken** returns STATUS_INVALID_PARAMETER. (This value is returned if the target token is not an impersonation token.) Otherwise, **SeFilterToken** returns STATUS_SUCCESS.

## -remarks

**SeFilterToken** can restrict the token in the following ways:

* Apply the deny-only attribute to SIDs in the token so they cannot be used to access secured objects. For more information about the deny-only attribute, see SID Attributes in an Access Token in the Microsoft Windows SDK documentation.

* Remove privileges from the token.

* Specify a list of restricting SIDs, which the system uses when it checks the token's access to a securable object. The system performs two access checks: one using the token's enabled SIDs, and another using the list of restricting SIDs. Access is granted only if both access checks allow the requested access rights.

The restricted token can be used together with [**SeCreateClientSecurity**](nf-ntifs-secreateclientsecurity.md) and [**SeImpersonateClientEx**](nf-ntifs-seimpersonateclientex.md) to create a process that has restricted access rights and privileges.

For more information about security and access control, see [Windows security model for driver developers](/windows-hardware/drivers/driversecurity/windows-security-model) and the documentation on these topics in the Windows SDK.

When the token returned in **NewToken** is no longer needed, free it by calling [**ObDereferenceObject**](../wdm/nf-wdm-obdereferenceobject.md).

## -see-also

[**LUID_AND_ATTRIBUTES**](../wdm/ns-wdm-_luid_and_attributes.md)

[**ObDereferenceObject**](../wdm/nf-wdm-obdereferenceobject.md)

[**ObReferenceObjectByHandle**](../wdm/nf-wdm-obreferenceobjectbyhandle.md)

[**SID**](ns-ntifs-_sid.md)

[**SID_AND_ATTRIBUTES**](ns-ntifs-_sid_and_attributes.md)

[**SeCreateClientSecurity**](nf-ntifs-secreateclientsecurity.md)

[**SeImpersonateClientEx**](nf-ntifs-seimpersonateclientex.md)

[**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md)

[**SeTokenIsRestricted**](nf-ntifs-setokenisrestricted.md)

[**TOKEN_GROUPS**](ns-ntifs-_token_groups.md)

[**TOKEN_PRIVILEGES**](ns-ntifs-_token_privileges.md)
