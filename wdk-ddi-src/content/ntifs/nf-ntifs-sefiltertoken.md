---
UID: NF:ntifs.SeFilterToken
title: SeFilterToken function
author: windows-driver-content
description: The SeFilterToken routine creates a new access token that is a restricted version of an existing access token.
old-location: ifsk\sefiltertoken.htm
tech.root: ifsk
ms.assetid: 2de3980a-da78-4cdd-916b-0801f38f3637
ms.date: 4/16/2018
ms.keywords: SeFilterToken, SeFilterToken routine [Installable File System Drivers], ifsk.sefiltertoken, ntifs/SeFilterToken, seref_33edad21-5cc4-4bd9-86f1-b52c648fc87c.xml
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows XP and later.
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	SeFilterToken
product:
- Windows
targetos: Windows
req.typenames: 
---

# SeFilterToken function


## -description


The <b>SeFilterToken</b> routine creates a new access token that is a restricted version of an existing access token. 


## -parameters




### -param ExistingToken [in]

Pointer to a primary or impersonation token. The token can also be a restricted token. This token must already be open for TOKEN_DUPLICATE access. This pointer can be obtained from an existing token handle by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a>, specifying TOKEN_DUPLICATE as the <i>DesiredAccess</i> type. 


### -param Flags [in]

Specifies additional privilege options. This parameter can be zero or a combination of the following values. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DISABLE_MAX_PRIVILEGE

</td>
<td>
Disables all privileges in the new token except SE_CHANGE_NOTIFY_PRIVILEGE. If this value is specified, the <i>PrivilegesToDelete</i> parameter is ignored. 

</td>
</tr>
<tr>
<td>
SANDBOX_INERT

</td>
<td>
Stores the TOKEN_SANDBOX_INERT flag in the token. 

</td>
</tr>
</table>
 


### -param SidsToDisable [in, optional]

Pointer to a TOKEN_GROUPS structure containing an array of SID_AND_ATTRIBUTES structures that specify the deny-only SIDs in the restricted token. The system uses a deny-only SID to deny access to a securable object. The absence of a deny-only SID does not allow access. 

Disabling a SID <u>turns on</u> SE_GROUP_USE_FOR_DENY_ONLY and <u>turns off</u> SE_GROUP_ENABLED and SE_GROUP_ENABLED_BY_DEFAULT. All other attributes are ignored 

Deny-only attributes apply to any combination of an existing token's SIDs, including the user SID and group SIDs that have the SE_GROUP_MANDATORY attribute. To get the SIDs associated with the existing token, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff556690">SeQueryInformationToken</a> with the TokenUser and TokenGroups flags. <b>SeFilterToken</b> ignores any SIDs in the array that are not also found in the existing token. 

<b>SeFilterToken</b> ignores the <b>Attributes</b> members of the SID_AND_ATTRIBUTES structures. 

This parameter is optional and can be <b>NULL</b>. 


### -param PrivilegesToDelete [in, optional]

Pointer to a TOKEN_PRIVILEGES structure containing an array of LUID_AND_ATTRIBUTES structures that specify the privileges to delete in the restricted token. 

To get the privileges held by the existing token, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff556690">SeQueryInformationToken</a> with the TokenPrivileges flag. <b>SeFilterToken</b> ignores any privileges in the array that are not held by the existing token. 

<b>SeFilterToken</b> ignores the <b>Attributes</b> members of the LUID_AND_ATTRIBUTES structures. 

This parameter is optional and can be <b>NULL</b>. 


### -param RestrictedSids [in, optional]

Pointer to a TOKEN_GROUPS structure containing an array of SID_AND_ATTRIBUTES structures that specify a list of restricting SIDs for the new token. If the existing token is a restricted token, the list of restricting SIDs for the new token is the intersection of this array and the list of restricting SIDs for the existing token. 

The <b>Attributes</b> members of the SID_AND_ATTRIBUTES structures must be zero. Restricting SIDs are always enabled for access checks. 

This parameter is optional and can be <b>NULL</b>. 


### -param FilteredToken

<p>Pointer to a caller-allocated variable that receives the address of the new restricted token. The new token is the same type, primary or impersonation, as the existing token. </p>




## -returns



If one or more of the parameter values were invalid, <b>SeFilterToken</b> returns STATUS_INVALID_PARAMETER. (This value is returned if the target token is not an impersonation token.) Otherwise, <b>SeFilterToken</b> returns STATUS_SUCCESS. 




## -remarks



<b>SeFilterToken</b> can restrict the token in the following ways: 

<ul>
<li>
Apply the deny-only attribute to SIDs in the token so they cannot be used to access secured objects. For more information about the deny-only attribute, see SID Attributes in an Access Token in the Microsoft Windows SDK documentation. 

</li>
<li>
Remove privileges from the token. 

</li>
<li>
Specify a list of restricting SIDs, which the system uses when it checks the token's access to a securable object. The system performs two access checks: one using the token's enabled SIDs, and another using the list of restricting SIDs. Access is granted only if both access checks allow the requested access rights.

</li>
</ul>
The restricted token can be used together with <a href="https://msdn.microsoft.com/library/windows/hardware/ff556595">SeCreateClientSecurity</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff556659">SeImpersonateClientEx</a> to create a process that has restricted access rights and privileges. 

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 

When the token returned in <i>NewToken</i> is no longer needed, free it by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549716">LUID_AND_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556742">SID_AND_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556595">SeCreateClientSecurity</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556659">SeImpersonateClientEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556690">SeQueryInformationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556724">SeTokenIsRestricted</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556834">TOKEN_GROUPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556846">TOKEN_PRIVILEGES</a>
 

 

