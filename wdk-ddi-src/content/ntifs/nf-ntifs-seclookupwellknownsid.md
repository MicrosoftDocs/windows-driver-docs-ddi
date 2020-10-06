---
UID: NF:ntifs.SecLookupWellKnownSid
title: SecLookupWellKnownSid function (ntifs.h)
description: SecLookupWellKnownSid accepts a well-known security identifier (SID) type as input and retrieves the local security identifier (SID) for this well known SID.
old-location: ifsk\seclookupwellknownsid.htm
tech.root: ifsk
ms.assetid: fbf06a28-d6f8-424c-95e0-ce24653cac64
ms.date: 04/16/2018
keywords: ["SecLookupWellKnownSid function"]
ms.keywords: SecLookupWellKnownSid, SecLookupWellKnownSid function [Installable File System Drivers], ifsk.seclookupwellknownsid, ksecddref_4c0053b3-cdaa-4cdc-a4d3-6329ccf64f98.xml, ntifs/SecLookupWellKnownSid
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This SecLookupWellKnownSid function is only available starting with Windows Server 2003.
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
req.lib: Ksecdd.lib
req.dll: 
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - SecLookupWellKnownSid
 - ntifs/SecLookupWellKnownSid
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ksecdd.lib
 - Ksecdd.dll
api_name:
 - SecLookupWellKnownSid
---

# SecLookupWellKnownSid function

## -description

**SecLookupWellKnownSid** accepts a well-known security identifier (SID) type as input and retrieves the local security identifier (SID) for this well known SID.

## -parameters

### -param SidType

[in] An enumerated type that indicates the type of security identifier (SID) the function returns. This parameter can be one of the following enumerations for WELL_KNOWN_SID_TYPE.

| Value | Meaning |
| ----- | ------- |
| WinNullSid | This value indicates a null SID. |
| WinWorldSid | This value indicates a SID that matches everyone. |
| WinLocalSid | This value indicates a local SID. |
| WinCreatorOwnerSid | Indicates a SID that matches the owner or creator of an object. This SID is used in inheritable access-control entries. |
| WinCreatorGroupSid | Indicates a SID that matches the creator group of an object. This SID is used in inheritable access-control entries. |
| WinCreatorOwnerServerSid | Indicates a creator owner server SID. |
| WinCreatorGroupServerSid | Indicates a creator group server SID. |
| WinNtAuthoritySid | Indicates a SID for the Windows NT authority. |
| WinDialupSid | Indicates a SID for a dial-up account. |
| WinNetworkSid | Indicates a SID for a network account. This SID is added to the process of a token when it logs on across a network. The corresponding logon type is LOGON32_LOGON_NETWORK. |
| WinBatchSid | Indicates a SID for a batch process. This SID is added to the process of a token when it logs on as a batch job. The corresponding logon type is LOGON32_LOGON_BATCH. |
| WinInteractiveSid | Indicates a SID for an interactive account. This SID is added to the process of a token when it logs on interactively. The corresponding logon type is LOGON32_LOGON_INTERACTIVE. |
| WinServiceSid | Indicates a SID for a service. This SID is added to the process of a token when it logs on as a service. The corresponding logon type is LOGON32_LOGON_SERVICE. |
| WinAnonymousSid | Indicates a SID for the anonymous account. |
| WinProxySid | Indicates a proxy SID. |
| WinEnterpriseControllersSid | Indicates a SID for an enterprise controller. |
| WinSelfSid | Indicates a SID for self. |
| WinAuthenticatedUserSid | Indicates a SID that matches any authenticated user. |
| WinRestrictedCodeSid | Indicates a SID for restricted code. |
| WinTerminalServerSid | Indicates a SID that matches a terminal server account. |
| WinRemoteLogonIdSid | Indicates a SID that matches remote logons. |
| WinLogonIdsSid | Indicates a SID that matches logon IDs. |
| WinLocalSystemSid | Indicates a SID that matches the local system. |
| WinLocalServiceSid | Indicates a SID that matches a local service. |
| WinNetworkServiceSid | Indicates a SID that matches a network service. |
| WinBuiltinDomainSid | Indicates a SID that matches the domain account. |
| WinBuiltinAdministratorsSid | Indicates a SID that matches the administrator account. |
| WinBuiltinUsersSid | Indicates a SID that matches built-in user accounts. |
| WinBuiltinGuestsSid | Indicates a SID that matches the guest account. |
| WinBuiltinPowerUsersSid | Indicates a SID that matches the power users group. |
| WinBuiltinAccountOperatorsSid | Indicates a SID that matches the account operators account. |
| WinBuiltinSystemOperatorsSid | Indicates a SID that matches the system operators group. |
| WinBuiltinPrintOperatorsSid | Indicates a SID that matches the print operators group. |
| WinBuiltinBackupOperatorsSid | Indicates a SID that matches the backup operators group. |
| WinBuiltinReplicatorSid | Indicates a SID that matches the replicator account. |
| WinBuiltinPreWindows2000CompatibleAccessSid | Indicates a SID that matches pre-Windows 2000 compatible accounts. |
| WinBuiltinRemoteDesktopUsersSid | Indicates a SID that matches remote desktop users. |
| WinBuiltinNetworkConfigurationOperatorsSid | Indicates a SID that matches the network operators group. |
| WinAccountAdministratorSid | Indicates a SID that matches the account administrators group. |
| WinAccountGuestSid | Indicates a SID that matches the account guest group. |
| WinAccountKrbtgtSid | Indicates a SID that matches account Kerberos target group. |
| WinAccountDomainAdminsSid | Indicates a SID that matches the account domain administrator group. |
| WinAccountDomainUsersSid | Indicates a SID that matches the account domain users group. |
| WinAccountDomainGuestsSid | Indicates a SID that matches the account domain guests group. |
| WinAccountComputersSid | Indicates a SID that matches the account computer group. |
| WinAccountControllersSid | Indicates a SID that matches the account controller group. |
| WinAccountCertAdminsSid | Indicates a SID that matches the certificate administrators group. |
| WinAccountSchemaAdminsSid | Indicates a SID that matches the schema administrators group. |
| WinAccountEnterpriseAdminsSid | Indicates a SID that matches the enterprise administrators group. |
| WinAccountPolicyAdminsSid | Indicates a SID that matches the policy administrators group. |
| WinAccountRasAndIasServersSid | Indicates a SID that matches the RAS and IAS server account. |
| WinNTLMAuthenticationSid | Indicates a SID present when the Microsoft NTLM authentication package authenticated the client. |
| WinDigestAuthenticationSid | Indicates a SID present when the Microsoft Digest authentication package authenticated the client. |
| WinSChannelAuthenticationSid | Indicates a SID present when the Secure Channel (SSL/TLS) authentication package authenticated the client. |
| WinThisOrganizationSid | Indicates a SID present when the user authenticated from within the forest or across a trust that does not have the selective authentication option enabled. If this SID is present, then WinOtherOrganizationSid cannot be present. |
| WinOtherOrganizationSid | Indicates a SID present when the user authenticated across a forest with the selective authentication option enabled. If this SID is present, then WinThisOrganizationSid cannot be present. |
| WinBuiltinIncomingForestTrustBuildersSid | Indicates a SID that allows a user to create incoming forest trusts. It is added to the token of users who are a member of the Incoming Forest Trust Builders built-in group in the root domain of the forest. |
| WinBuiltinPerfMonitoringUsersSid | Indicates a SID that matches the performance monitor user group. |
| WinBuiltinPerfLoggingUsersSid | Indicates a SID that matches the performance log user group. |
| WinBuiltinAuthorizationAccessSid | Indicates a SID that matches the Windows Authorization Access group. |
| WinBuiltinTerminalServerLicenseServersSid | Indicates a SID is present in a server that can issue Terminal Server licenses. |
| WinBuiltinDCOMUsersSid | Indicates a SID that matches the DCOM users group. |

### -param Sid

[out] A pointer to a buffer that receives the SID structure that corresponds to the *SidType* parameter. If this parameter is **NULL**, *SidBufferSize* must be zero.

### -param SidBufferSize

[in] A variable that specifies the size of the *Sid* buffer in bytes.

### -param OPTIONAL

An optional pointer to a variable that specifies the size of the *Sid* buffer. If the function fails because the buffer is too small or if *SidBufferSize* is zero, this variable receives the required buffer size. On success, this variable contains the size of the returned *Sid*.

## -returns

**SecLookupWellKnownSid** returns STATUS_SUCCESS on success or one of the following error codes on failure:

| Return code | Description |
| ----------- | ----------- |
| SEC_E_INTERNAL_ERROR | An internal error occurred while trying to connect to the Local System Authority (LSA) or the local procedure call (LPC) to the security provider failed. |
| STATUS_ACCESS_DENIED | The process ID associated with the currently executing thread does not match the current process ID. |
| STATUS_BUFFER_TOO_SMALL | The buffer size for the *Sid*, the *SidBufferSize* parameter, was too small. |
| STATUS_INVALID_PARAMETER | A **NULL** pointer was passed for *Sid* parameter or a well-known SID could not be found for the *SidType* specified. |
| STATUS_PROCESS_IS_TERMINATING | This process has terminated so it is not possible to establish a local procedure call (LPC) connection. |

## -remarks

**SecLookupWellKnownSid** attempts to find a well known SID using a *SidType* parameter. In addition to looking up well-known SIDs on the local machine, **SecLookupWellKnownSid** can look up well-known SIDs on the local domain. **SecLookupWellKnownSid**first checks a list of well-known local SIDs. If the *SidType* does not correspond to a local well-known SID, the function checks for well-known SIDs on the primary domain.

If the function cannot find the well known SID for the *SidType* specified, **SecLookupWellKnownSid** fails. This can occur if a network time-out prevents the function from finding the SID on the primary domain. It also occurs for a *SidType* that has no corresponding well-known SID.

**SecLookupWellKnownSid** is equivalent to the Win32   **CreateWellKnownSid** function. For user-mode applications, the WELL_KNOWN_SID_TYPE enumeration is defined in *winbase.h*.

**SecLookupWellKnownSid** is exported by the ksecdd driver, which implements this function by using user-mode helper services. Accordingly, the use of this function within file systems must obey the usual rules for communication with user-mode services. **SecLookupWellKnownSid** cannot be used during paging file I/O.

## -see-also

[SID](ns-ntifs-_sid.md)

[**SecLookupAccountName**](/previous-versions/ff554795(v=vs.85))

[**SecLookupAccountSid**](/previous-versions/ff556579(v=vs.85))
