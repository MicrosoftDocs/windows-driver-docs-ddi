---
UID: NF:ntifs.SeFilterToken
title: SeFilterToken function
author: windows-driver-content
description: The SeFilterToken routine creates a new access token that is a restricted version of an existing access token.
old-location: ifsk\sefiltertoken.htm
old-project: ifsk
ms.assetid: 2de3980a-da78-4cdd-916b-0801f38f3637
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntifs/SeFilterToken, SeFilterToken, seref_33edad21-5cc4-4bd9-86f1-b52c648fc87c.xml, SeFilterToken routine [Installable File System Drivers], ifsk.sefiltertoken
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	SeFilterToken
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SeFilterToken function


## -description


The <b>SeFilterToken</b> routine creates a new access token that is a restricted version of an existing access token. 


## -syntax


````
NTSTATUS SeFilterToken(
  _In_     PACCESS_TOKEN     ExistingToken,
  _In_     ULONG             Flags,
  _In_opt_ PTOKEN_GROUPS     SidsToDisable,
  _In_opt_ PTOKEN_PRIVILEGES PrivilegesToDelete,
  _In_opt_ PTOKEN_GROUPS     RestrictedSids,
  _Out_    PACCESS_TOKEN     *NewToken
);
````


## -parameters




### -param ExistingToken [in]

Pointer to a primary or impersonation token. The token can also be a restricted token. This token must already be open for TOKEN_DUPLICATE access. This pointer can be obtained from an existing token handle by calling <a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>, specifying TOKEN_DUPLICATE as the <i>DesiredAccess</i> type. 


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

Deny-only attributes apply to any combination of an existing token's SIDs, including the user SID and group SIDs that have the SE_GROUP_MANDATORY attribute. To get the SIDs associated with the existing token, call <a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a> with the TokenUser and TokenGroups flags. <b>SeFilterToken</b> ignores any SIDs in the array that are not also found in the existing token. 

<b>SeFilterToken</b> ignores the <b>Attributes</b> members of the SID_AND_ATTRIBUTES structures. 

This parameter is optional and can be <b>NULL</b>. 


### -param PrivilegesToDelete [in, optional]

Pointer to a TOKEN_PRIVILEGES structure containing an array of LUID_AND_ATTRIBUTES structures that specify the privileges to delete in the restricted token. 

To get the privileges held by the existing token, call <a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a> with the TokenPrivileges flag. <b>SeFilterToken</b> ignores any privileges in the array that are not held by the existing token. 

<b>SeFilterToken</b> ignores the <b>Attributes</b> members of the LUID_AND_ATTRIBUTES structures. 

This parameter is optional and can be <b>NULL</b>. 


### -param RestrictedSids [in, optional]

Pointer to a TOKEN_GROUPS structure containing an array of SID_AND_ATTRIBUTES structures that specify a list of restricting SIDs for the new token. If the existing token is a restricted token, the list of restricting SIDs for the new token is the intersection of this array and the list of restricting SIDs for the existing token. 

The <b>Attributes</b> members of the SID_AND_ATTRIBUTES structures must be zero. Restricting SIDs are always enabled for access checks. 

This parameter is optional and can be <b>NULL</b>. 


### -param FilteredToken

TBD



#### - NewToken [out]

Pointer to a caller-allocated variable that receives the address of the new restricted token. The new token is the same type, primary or impersonation, as the existing token. 


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
</ul>The restricted token can be used together with <a href="..\ntifs\nf-ntifs-secreateclientsecurity.md">SeCreateClientSecurity</a> and <a href="..\ntifs\nf-ntifs-seimpersonateclientex.md">SeImpersonateClientEx</a> to create a process that has restricted access rights and privileges. 

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 

When the token returned in <i>NewToken</i> is no longer needed, free it by calling <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>.



## -see-also

<a href="..\ntifs\nf-ntifs-seimpersonateclientex.md">SeImpersonateClientEx</a>

<a href="..\ntifs\ns-ntifs-_token_privileges.md">TOKEN_PRIVILEGES</a>

<a href="..\wdm\ns-wdm-_luid_and_attributes.md">LUID_AND_ATTRIBUTES</a>

<a href="..\ntifs\nf-ntifs-setokenisrestricted.md">SeTokenIsRestricted</a>

<a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>

<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>

<a href="..\ntifs\ns-ntifs-_sid_and_attributes.md">SID_AND_ATTRIBUTES</a>

<a href="..\ntifs\nf-ntifs-secreateclientsecurity.md">SeCreateClientSecurity</a>

<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>

<a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>

<a href="..\ntifs\ns-ntifs-_token_groups.md">TOKEN_GROUPS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeFilterToken routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

