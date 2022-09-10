---
UID: NE:ntifs._TOKEN_INFORMATION_CLASS
title: TOKEN_INFORMATION_CLASS (ntifs.h)
description: The TOKEN_INFORMATION_CLASS enumeration type contains values that specify the type of information being assigned to or retrieved from an access token.
old-location: ifsk\token_information_class.htm
tech.root: ifsk
ms.date: 05/24/2022
keywords: ["TOKEN_INFORMATION_CLASS enumeration"]
ms.keywords: "*PTOKEN_INFORMATION_CLASS, MaxTokenInfoClass, PTOKEN_INFORMATION_CLASS, PTOKEN_INFORMATION_CLASS enumeration pointer [Installable File System Drivers], TOKEN_INFORMATION_CLASS, TOKEN_INFORMATION_CLASS enumeration [Installable File System Drivers], TokenAccessInformation, TokenAppContainerNumber, TokenAppContainerSid, TokenAuditPolicy, TokenCapabilities, TokenDefaultDacl, TokenDeviceClaimAttributes, TokenDeviceGroups, TokenElevation, TokenGroups, TokenGroupsAndPrivileges, TokenHasRestrictions, TokenImpersonationLevel, TokenIntegrityLevel, TokenIsAppContainer, TokenIsRestricted, TokenLinkedToken, TokenLogonSid, TokenMandatoryPolicy, TokenOrigin, TokenOwner, TokenPrimaryGroup, TokenPrivileges, TokenProcessTrustLevel, TokenRestrictedDeviceClaimAttributes, TokenRestrictedDeviceGroups, TokenRestrictedSids, TokenRestrictedUserClaimAttributes, TokenSandBoxInert, TokenSecurityAttributes, TokenSessionId, TokenSessionReference, TokenSource, TokenStatistics, TokenType, TokenUIAccess, TokenUser, TokenUserClaimAttributes, TokenVirtualizationAllowed, TokenVirtualizationEnabled, _TOKEN_INFORMATION_CLASS, ifsk.token_information_class, ntifs/MaxTokenInfoClass, ntifs/PTOKEN_INFORMATION_CLASS, ntifs/TOKEN_INFORMATION_CLASS, ntifs/TokenAccessInformation, ntifs/TokenAppContainerNumber, ntifs/TokenAppContainerSid, ntifs/TokenAuditPolicy, ntifs/TokenCapabilities, ntifs/TokenDefaultDacl, ntifs/TokenDeviceClaimAttributes, ntifs/TokenDeviceGroups, ntifs/TokenElevation, ntifs/TokenGroups, ntifs/TokenGroupsAndPrivileges, ntifs/TokenHasRestrictions, ntifs/TokenImpersonationLevel, ntifs/TokenIntegrityLevel, ntifs/TokenIsAppContainer, ntifs/TokenIsRestricted, ntifs/TokenLinkedToken, ntifs/TokenLogonSid, ntifs/TokenMandatoryPolicy, ntifs/TokenOrigin, ntifs/TokenOwner, ntifs/TokenPrimaryGroup, ntifs/TokenPrivileges, ntifs/TokenProcessTrustLevel, ntifs/TokenRestrictedDeviceClaimAttributes, ntifs/TokenRestrictedDeviceGroups, ntifs/TokenRestrictedSids, ntifs/TokenRestrictedUserClaimAttributes, ntifs/TokenSandBoxInert, ntifs/TokenSecurityAttributes, ntifs/TokenSessionId, ntifs/TokenSessionReference, ntifs/TokenSource, ntifs/TokenStatistics, ntifs/TokenType, ntifs/TokenUIAccess, ntifs/TokenUser, ntifs/TokenUserClaimAttributes, ntifs/TokenVirtualizationAllowed, ntifs/TokenVirtualizationEnabled, securitystructures_525fb6c8-0030-40ea-927a-72fe89eff87e.xml"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: TOKEN_INFORMATION_CLASS, *PTOKEN_INFORMATION_CLASS
f1_keywords:
 - _TOKEN_INFORMATION_CLASS
 - ntifs/_TOKEN_INFORMATION_CLASS
 - PTOKEN_INFORMATION_CLASS
 - ntifs/PTOKEN_INFORMATION_CLASS
 - TOKEN_INFORMATION_CLASS
 - ntifs/TOKEN_INFORMATION_CLASS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _TOKEN_INFORMATION_CLASS
 - PTOKEN_INFORMATION_CLASS
 - TOKEN_INFORMATION_CLASS
---

# TOKEN_INFORMATION_CLASS enumeration

## -description

The **TOKEN_INFORMATION_CLASS** enumeration type contains values that specify the type of information being assigned to or retrieved from an access token.

[**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md) and [**ZwQueryInformationToken**](nf-ntifs-zwqueryinformationtoken.md) use **TOKEN_INFORMATION_CLASS** values to indicate the type of token information to retrieve.

## -enum-fields

### -field TokenUser

The buffer receives a [**TOKEN_USER**](ns-ntifs-_token_user.md) structure containing the token's user account.

### -field TokenGroups

The buffer receives a [**TOKEN_GROUPS**](ns-ntifs-_token_groups.md) structure containing the group accounts associated with the token.

### -field TokenPrivileges

The buffer receives a [**TOKEN_PRIVILEGES**](ns-ntifs-_token_privileges.md) structure containing the token's privileges.

### -field TokenOwner

The buffer receives a [**TOKEN_OWNER**](ns-ntifs-_token_owner.md) structure containing the default owner SID for newly created objects.

### -field TokenPrimaryGroup

The buffer receives a [**TOKEN_PRIMARY_GROUP**](ns-ntifs-_token_primary_group.md) structure containing the default primary group SID for newly created objects.

### -field TokenDefaultDacl

The buffer receives a [**TOKEN_DEFAULT_DACL**](ns-ntifs-_token_default_dacl.md) structure containing the default discretionary ACL (DACL)) for newly created objects.

### -field TokenSource

The buffer receives a [**TOKEN_SOURCE**](ns-ntifs-_token_source.md) structure containing the source of the token. TOKEN_QUERY_SOURCE access is needed to retrieve this information.

### -field TokenType

The buffer receives a [**TOKEN_TYPE**](ne-ntifs-_token_type.md) value indicating whether the token is a primary or impersonation token.

### -field TokenImpersonationLevel

The buffer receives a [**SECURITY_IMPERSONATION_LEVEL**](../wdm/ne-wdm-_security_impersonation_level.md) value indicating the impersonation level of the token. If the access token is not an impersonation token, the call to [**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md) or [**ZwQueryInformationToken**](nf-ntifs-zwqueryinformationtoken.md) fails.

### -field TokenStatistics

The buffer receives a [**TOKEN_STATISTICS**](ns-ntifs-_token_statistics.md) structure containing various token statistics.

### -field TokenRestrictedSids

The buffer receives a [**TOKEN_GROUPS**](ns-ntifs-_token_groups.md) structure containing the list of restricting SIDs in a restricted token. This value is valid starting with Windows Vista.

### -field TokenSessionId

The buffer receives a DWORD value that indicates the Terminal Services session identifier associated with the token. If the token is associated with the Terminal Server console session, the session identifier is zero. A nonzero session identifier indicates a Terminal Services client session. In a non-Terminal Services environment, the session identifier is zero. This value is valid starting with Windows Vista.

### -field TokenGroupsAndPrivileges

The buffer receives a [**TOKEN_GROUPS_AND_PRIVILEGES**](ns-ntifs-_token_groups_and_privileges.md) structure that contains the user SID, the group accounts, the restricted SIDs, and the authentication ID associated with the token. This value is valid starting with Windows Vista.

### -field TokenSessionReference

Reserved for system use.

### -field TokenSandBoxInert

The buffer receives a DWORD value that is nonzero if the token includes the SANDBOX_INERT flag. This value is valid starting with Windows Vista.

### -field TokenAuditPolicy

Reserved for system use.

### -field TokenOrigin

The buffer receives a [**TOKEN_ORIGIN**](ns-ntifs-_token_origin.md) value.

If the token resulted from a logon that used explicit credentials, such as passing a name, domain, and password to the user-mode [**LogonUser**](/windows/win32/api/winbase/nf-winbase-logonusera) function, then the **TOKEN_ORIGIN** structure will contain the ID of the logon session that created it.

If the token resulted from network authentication, such as a call to user-mode **AcceptSecurityContext** function or a call to user-mode **LogonUser** function with dwLogonType set to LOGON32_LOGON_NETWORK or LOGON32_LOGON_NETWORK_CLEARTEXT, then this value will be zero.

 This value is valid starting with Windows Server 2003.

### -field TokenElevationType

### -field TokenLinkedToken

The buffer receives a [**TOKEN_LINKED_TOKEN**](/windows/win32/api/winnt/ns-winnt-token_linked_token) structure that contains a handle to another token that is linked to this token. This value is valid starting with Windows Vista.

### -field TokenElevation

The buffer receives a [**TOKEN_ELEVATION**](/windows/win32/api/winnt/ns-winnt-token_elevation) structure that specifies whether the token is elevated. This value is valid starting with Windows Vista.

### -field TokenHasRestrictions

The buffer receives a **DWORD** value that is nonzero if the token has ever been filtered. This value is valid starting with Windows Vista.

### -field TokenAccessInformation

The buffer receives a [**TOKEN_ACCESS_INFORMATION**](/windows/win32/api/winnt/ns-winnt-token_access_information) structure that specifies  security information contained in the token. This value is valid starting with Windows Vista.

### -field TokenVirtualizationAllowed

The buffer receives a **DWORD** value that is nonzero if [**virtualization**](/previous-versions/windows/hardware/design/dn614617(v=vs.85)) is allowed for the token. This value is valid starting with Windows Vista.

### -field TokenVirtualizationEnabled

The buffer receives a **DWORD** value that is nonzero if [**virtualization**](/previous-versions/windows/hardware/design/dn614617(v=vs.85)) is enabled for the token. This value is valid starting with Windows Vista.

### -field TokenIntegrityLevel

The buffer receives a [**TOKEN_MANDATORY_LABEL**](/windows/win32/api/winnt/ns-winnt-token_mandatory_label) structure that specifies the token's integrity level. This value is valid starting with Windows Vista. For [**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md) the output is the actual integrity level  (**DWORD**).

### -field TokenUIAccess

The buffer receives a **DWORD** value that is nonzero if  the token has the UIAccess flag set. This value is valid starting with Windows Vista.

### -field TokenMandatoryPolicy

The buffer receives a [**TOKEN_MANDATORY_POLICY**](/windows/win32/api/winnt/ns-winnt-token_mandatory_policy) structure that specifies the token's mandatory integrity policy. This value is valid starting with Windows Vista.

### -field TokenLogonSid

The buffer receives a [**TOKEN_GROUPS**](ns-ntifs-_token_groups.md) structure that specifies the token's logon SID. This value is valid starting with Windows Vista.

### -field TokenIsAppContainer

The buffer receives a **DWORD** value that is nonzero if  the token has the application container flag set. This value is valid starting with Windows 8.

### -field TokenCapabilities

The buffer receives a **TOKEN_GROUPS** structure and an array of **SID_AND_ATTRIBUTES** structures for each token capability. This value is valid starting with Windows 8.

### -field TokenAppContainerSid

The buffer receives a **TOKEN_APPCONTAINER_INFORMATION** structure that contains the AppContainerSid associated with the token. If the token is not associated with an app container, the TokenAppContainer member of the **TOKEN_APPCONTAINER_INFORMATION** structure points to NULL. This value is valid starting with Windows 8.

### -field TokenAppContainerNumber

The buffer receives a **DWORD** value that is the application container number. This value is valid starting with Windows 8.

### -field TokenUserClaimAttributes

The buffer receives a [**CLAIM_SECURITY_ATTRIBUTES_INFORMATION**](/windows/win32/api/winnt/ns-winnt-token_mandatory_policy) structure that specifies the user's claim attributes. This value is valid starting with Windows 8.

### -field TokenDeviceClaimAttributes

The buffer receives a [**CLAIM_SECURITY_ATTRIBUTES_INFORMATION**](/windows/win32/api/winnt/ns-winnt-token_mandatory_policy) structure that specifies the device's claim attributes. This value is valid starting with Windows 8.

### -field TokenRestrictedUserClaimAttributes

Reserved for system use.

### -field TokenRestrictedDeviceClaimAttributes

Reserved for system use.

### -field TokenDeviceGroups

The buffer receives a **TOKEN_GROUPS** structure and an array of **SID_AND_ATTRIBUTES** structures for each device group. This value is valid starting with Windows 8.

### -field TokenRestrictedDeviceGroups

Reserved for system use.

### -field TokenSecurityAttributes

Reserved for system use.

### -field TokenIsRestricted

Reserved for system use.

### -field TokenProcessTrustLevel

Reserved for system use.

### -field TokenPrivateNameSpace

### -field TokenSingletonAttributes

### -field TokenBnoIsolation

### -field TokenChildProcessFlags

### -field TokenIsLessPrivilegedAppContainer

### -field TokenIsSandboxed

### -field TokenIsAppSilo

### -field MaxTokenInfoClass

The maximum value for this enumeration.

## -see-also

[**ACL**](../wdm/ns-wdm-_acl.md)

[**SECURITY_IMPERSONATION_LEVEL**](../wdm/ne-wdm-_security_impersonation_level.md)

[**SID**](ns-ntifs-_sid.md)

[**SeFilterToken**](nf-ntifs-sefiltertoken.md)

[**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md)

[**SeTokenIsRestricted**](nf-ntifs-setokenisrestricted.md)

[**TOKEN_DEFAULT_DACL**](ns-ntifs-_token_default_dacl.md)

[**TOKEN_GROUPS**](ns-ntifs-_token_groups.md)

[**TOKEN_ORIGIN**](ns-ntifs-_token_origin.md)

[**TOKEN_OWNER**](ns-ntifs-_token_owner.md)

[**TOKEN_PRIMARY_GROUP**](ns-ntifs-_token_primary_group.md)

[**TOKEN_PRIVILEGES**](ns-ntifs-_token_privileges.md)

[**TOKEN_SOURCE**](ns-ntifs-_token_source.md)

[**TOKEN_STATISTICS**](ns-ntifs-_token_statistics.md)

[**TOKEN_TYPE**](ne-ntifs-_token_type.md)

[**TOKEN_USER**](ns-ntifs-_token_user.md)

[**ZwQueryInformationToken**](nf-ntifs-zwqueryinformationtoken.md)

[**ZwSetInformationToken**](nf-ntifs-zwsetinformationtoken.md)
