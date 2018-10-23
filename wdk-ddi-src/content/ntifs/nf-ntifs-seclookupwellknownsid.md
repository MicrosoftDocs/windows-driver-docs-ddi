---
UID: NF:ntifs.SecLookupWellKnownSid
title: SecLookupWellKnownSid function
author: windows-driver-content
description: SecLookupWellKnownSid accepts a well-known security identifier (SID) type as input and retrieves the local security identifier (SID) for this well known SID.
old-location: ifsk\seclookupwellknownsid.htm
tech.root: ifsk
ms.assetid: fbf06a28-d6f8-424c-95e0-ce24653cac64
ms.date: 04/16/2018
ms.keywords: SecLookupWellKnownSid, SecLookupWellKnownSid function [Installable File System Drivers], ifsk.seclookupwellknownsid, ksecddref_4c0053b3-cdaa-4cdc-a4d3-6329ccf64f98.xml, ntifs/SecLookupWellKnownSid
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ksecdd.lib
-	Ksecdd.dll
api_name:
-	SecLookupWellKnownSid
product:
- Windows
targetos: Windows
req.typenames: 
---

# SecLookupWellKnownSid function


## -description


<b>SecLookupWellKnownSid</b> accepts a well-known security identifier (SID) type as input and retrieves the local security identifier (SID) for this well known SID.


## -parameters




### -param SidType [in]

An enumerated type that indicates the type of security identifier (SID) the function returns. This parameter can be one of the following enumerations for WELL_KNOWN_SID_TYPE:





#### WinNullSid

This value indicates a null SID. 



#### WinWorldSid

This value indicates a SID that matches everyone.



#### WinLocalSid

This value indicates a local SID.



#### WinCreatorOwnerSid

This value indicates a SID that matches the owner or creator of an object. This SID is used in inheritable access-control entries.



#### WinCreatorGroupSid

This value indicates a SID that matches the creator group of an object. This SID is used in inheritable access-control entries.



#### WinCreatorOwnerServerSid

This value indicates a creator owner server SID. 



#### WinCreatorGroupServerSid

This value indicates a creator group server SID.



#### WinNtAuthoritySid

This value indicates a SID for the Windows NT authority.



#### WinDialupSid

This value indicates a SID for a dial-up account.



#### WinNetworkSid

This value indicates a SID for a network account. This SID is added to the process of a token when it logs on across a network. The corresponding logon type is LOGON32_LOGON_NETWORK. 



#### WinBatchSid

This value indicates a SID for a batch process. This SID is added to the process of a token when it logs on as a batch job. The corresponding logon type is LOGON32_LOGON_BATCH. 



#### WinInteractiveSid

This value indicates a SID for an interactive account. This SID is added to the process of a token when it logs on interactively. The corresponding logon type is LOGON32_LOGON_INTERACTIVE. 



#### WinServiceSid

This value indicates a SID for a service. This SID is added to the process of a token when it logs on as a service. The corresponding logon type is LOGON32_LOGON_SERVICE. 



#### WinAnonymousSid

This value indicates a SID for the anonymous account. 



#### WinProxySid

This value indicates a proxy SID. 



#### WinEnterpriseControllersSid

This value indicates a SID for an enterprise controller.



#### WinSelfSid

This value indicates a SID for self.



#### WinAuthenticatedUserSid

This value indicates a SID that matches any authenticated user.



#### WinRestrictedCodeSid

This value indicates a SID for restricted code.



#### WinTerminalServerSid

This value indicates a SID that matches a terminal server account.



#### WinRemoteLogonIdSid

This value indicates a SID that matches remote logons.



#### WinLogonIdsSid

This value indicates a SID that matches logon IDs.



#### WinLocalSystemSid

This value indicates a SID that matches the local system.



#### WinLocalServiceSid

This value indicates a SID that matches a local service.



#### WinNetworkServiceSid

This value indicates a SID that matches a network service.



#### WinBuiltinDomainSid

This value indicates a SID that matches the domain account.



#### WinBuiltinAdministratorsSid

This value indicates a SID that matches the administrator account.



#### WinBuiltinUsersSid

This value indicates a SID that matches built-in user accounts. 



#### WinBuiltinGuestsSid

This value indicates a SID that matches the guest account.



#### WinBuiltinPowerUsersSid

This value indicates a SID that matches the power users group.



#### WinBuiltinAccountOperatorsSid

This value indicates a SID that matches the account operators account.



#### WinBuiltinSystemOperatorsSid

This value indicates a SID that matches the system operators group.



#### WinBuiltinPrintOperatorsSid

This value indicates a SID that matches the print operators group.



#### WinBuiltinBackupOperatorsSid

This value indicates a SID that matches the backup operators group.



#### WinBuiltinReplicatorSid

This value indicates a SID that matches the replicator account.



#### WinBuiltinPreWindows2000CompatibleAccessSid

This value indicates a SID that matches pre-Windows 2000 compatible accounts.



#### WinBuiltinRemoteDesktopUsersSid

This value indicates a SID that matches remote desktop users.



#### WinBuiltinNetworkConfigurationOperatorsSid

This value indicates a SID that matches the network operators group.



#### WinAccountAdministratorSid

This value indicates a SID that matches the account administrators group.



#### WinAccountGuestSid

This value indicates a SID that matches the account guest group.



#### WinAccountKrbtgtSid

This value indicates a SID that matches account Kerberos target group.



#### WinAccountDomainAdminsSid

This value indicates a SID that matches the account domain administrator group.



#### WinAccountDomainUsersSid

This value indicates a SID that matches the account domain users group.



#### WinAccountDomainGuestsSid

This value indicates a SID that matches the account domain guests group.



#### WinAccountComputersSid

This value indicates a SID that matches the account computer group.



#### WinAccountControllersSid

This value indicates a SID that matches the account controller group.



#### WinAccountCertAdminsSid

This value indicates a SID that matches the certificate administrators group. 



#### WinAccountSchemaAdminsSid

This value indicates a SID that matches the schema administrators group.



#### WinAccountEnterpriseAdminsSid

This value indicates a SID that matches the enterprise administrators group.



#### WinAccountPolicyAdminsSid

This value indicates a SID that matches the policy administrators group.



#### WinAccountRasAndIasServersSid

This value indicates a SID that matches the RAS and IAS server account.



#### WinNTLMAuthenticationSid

This value indicates a SID present when the Microsoft NTLM authentication package authenticated the client.



#### WinDigestAuthenticationSid

This value indicates a SID present when the Microsoft Digest authentication package authenticated the client.



#### WinSChannelAuthenticationSid

This value indicates a SID present when the Secure Channel (SSL/TLS) authentication package authenticated the client.



#### WinThisOrganizationSid

This value indicates a SID present when the user authenticated from within the forest or across a trust that does not have the selective authentication option enabled. If this SID is present, then WinOtherOrganizationSid cannot be present.



#### WinOtherOrganizationSid

This value indicates a SID present when the user authenticated across a forest with the selective authentication option enabled. If this SID is present, then WinThisOrganizationSid cannot be present.



#### WinBuiltinIncomingForestTrustBuildersSid

This value indicates a SID that allows a user to create incoming forest trusts. It is added to the token of users who are a member of the Incoming Forest Trust Builders built-in group in the root domain of the forest.



#### WinBuiltinPerfMonitoringUsersSid

This value indicates a SID that matches the performance monitor user group.



#### WinBuiltinPerfLoggingUsersSid

This value indicates a SID that matches the performance log user group.



#### WinBuiltinAuthorizationAccessSid

This value indicates a SID that matches the Windows Authorization Access group.



#### WinBuiltinTerminalServerLicenseServersSid

This value indicates a SID is present in a server that can issue Terminal Server licenses.



#### WinBuiltinDCOMUsersSid

This value indicates a SID that matches the DCOM users group.


### -param Sid [out]


      A pointer to a buffer that receives the SID structure that corresponds to the <i>SidType</i> parameter. If this parameter is <b>NULL</b>, <i>SidBufferSize</i> must be zero. 
     


### -param SidBufferSize [in]

A variable that specifies the size of the <i>Sid</i> buffer in bytes.


### -param OPTIONAL

<p>An optional pointer to a variable that specifies the size of the <i>Sid</i> buffer. If the function fails because the buffer is too small or if <i>SidBufferSize</i> is zero, this variable receives the required buffer size. On success, this variable contains the size of the returned <i>Sid</i></p>




## -returns



<b>SecLookupWellKnownSid</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>SEC_E_INTERNAL_ERROR</b></dt>
</dl>
</td>
<td width="60%">
An internal error occurred while trying to connect to the Local System Authority (LSA) or the local procedure call (LPC) to the security provider failed. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The process ID associated with the currently executing thread does not match the current process ID. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer size for the <i>Sid</i>, the <i>SidBufferSize</i> parameter, was too small.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A <b>NULL</b> pointer was passed for <i>Sid</i> parameter or a well-known SID could not be found for the <i>SidType</i> specified. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PROCESS_IS_TERMINATING</b></dt>
</dl>
</td>
<td width="60%">
This process has terminated so it is not possible to establish a local procedure call (LPC) connection.

</td>
</tr>
</table>
 




## -remarks



<b>SecLookupWellKnownSid</b> attempts to find a well known SID using a <i>SidType</i> parameter. In addition to looking up well-known SIDs on the local machine, <b>SecLookupWellKnownSid</b> can look up well-known SIDs on the local domain. <b>SecLookupWellKnownSid</b>first checks a list of well-known local SIDs. If the <i>SidType</i> does not correspond to a local well-known SID, the function checks for well-known SIDs on the primary domain. 

If the function cannot find the well known SID for the <i>SidType</i> specified, <b>SecLookupWellKnownSid</b> fails. This can occur if a network time-out prevents the function from finding the SID on the primary domain. It also occurs for a <i>SidType</i> that has no corresponding well-known SID.

<b>SecLookupWellKnownSid</b> is equivalent to the Win32   <b>CreateWellKnownSid</b> function. For user-mode applications, the WELL_KNOWN_SID_TYPE enumeration is defined in <i>winbase.h</i>.

<b>SecLookupWellKnownSid</b> is exported by the ksecdd driver, which implements this function by using user-mode helper services. Accordingly, the use of this function within file systems must obey the usual rules for communication with user-mode services. <b>SecLookupWellKnownSid</b> cannot be used during paging file I/O. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554795">SecLookupAccountName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556579">SecLookupAccountSid</a>
 

 

