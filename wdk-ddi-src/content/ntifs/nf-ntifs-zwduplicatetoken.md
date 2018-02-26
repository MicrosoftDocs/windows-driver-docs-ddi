---
UID: NF:ntifs.ZwDuplicateToken
title: ZwDuplicateToken function
author: windows-driver-content
description: The ZwDuplicateToken function creates a handle to a new access token that duplicates an existing token. This function can create either a primary token or an impersonation token.
old-location: kernel\zwduplicatetoken.htm
old-project: kernel
ms.assetid: 89cc86aa-8ab0-4614-b92d-a1c627490d8d
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , D, NtDuplicateToken, T, Z, ZwDuplicateToken, ZwDuplicateToken function [Kernel-Mode Driver Architecture], a, c, e, i, k, k111_5c46bc83-ec51-45f5-a3fc-e199f91d58ce.xml, kernel.zwduplicatetoken, l, n, ntifs/NtDuplicateToken, ntifs/ZwDuplicateToken, o, p, t, u, w"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ZwDuplicateToken
-	NtDuplicateToken
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# ZwDuplicateToken function


## -description


The <b>ZwDuplicateToken</b> function creates a handle to a new <a href="http://go.microsoft.com/fwlink/p/?linkid=96098">access token</a> that duplicates an existing token. This function can create either a primary token or an impersonation token. 


## -syntax


````
NTSTATUS ZwDuplicateToken(
  _In_  HANDLE             ExistingTokenHandle,
  _In_  ACCESS_MASK        DesiredAccess,
  _In_  POBJECT_ATTRIBUTES ObjectAttributes,
  _In_  BOOLEAN            EffectiveOnly,
  _In_  TOKEN_TYPE         TokenType,
  _Out_ PHANDLE            NewTokenHandle
);
````


## -parameters




### -param ExistingTokenHandle [in]

A handle to an existing access token that was opened with the TOKEN_DUPLICATE access right. This parameter is required and cannot be <b>NULL</b>.


### -param DesiredAccess [in]

Bitmask that specifies the requested access rights for the new token. <b>ZwDuplicateToken</b> compares the requested access rights with the existing token's discretionary access control list (DACL) to determine which rights are granted or denied to the new token. To request the same access rights as the existing token, specify zero. To request all access rights that are valid for the caller, specify MAXIMUM_ALLOWED. This parameter is optional and can either be zero, MAXIMUM_ALLOWED, or a bitwise OR combination of one or more of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DELETE

</td>
<td>
Required to delete the object.

</td>
</tr>
<tr>
<td>
READ_CONTROL

</td>
<td>
Required to read the DACL and ownership information for the object. For access to the system access control list (SACL), see ACCESS_SYSTEM_SECURITY later in this table.

</td>
</tr>
<tr>
<td>
WRITE_DAC

</td>
<td>
Required to change the DACL information for the object.

</td>
</tr>
<tr>
<td>
WRITE_OWNER

</td>
<td>
Required to change the ownership information in the object's security descriptor (<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>).

</td>
</tr>
<tr>
<td>
ACCESS_SYSTEM_SECURITY

</td>
<td>
Required to get or set the SACL in an object's ACL. The operating system grants this right to the new token only if the SE_SECURITY_NAME privilege is enabled in the access token of the calling thread.

</td>
</tr>
<tr>
<td>
STANDARD_RIGHTS_READ

</td>
<td>
Currently defined to equal READ_CONTROL.

</td>
</tr>
<tr>
<td>
STANDARD_RIGHTS_WRITE

</td>
<td>
Currently defined to equal READ_CONTROL.

</td>
</tr>
<tr>
<td>
STANDARD_RIGHTS_EXECUTE

</td>
<td>
Currently defined to equal READ_CONTROL.

</td>
</tr>
<tr>
<td>
STANDARD_RIGHTS_REQUIRED

</td>
<td>
Combines DELETE, READ_CONTROL, WRITE_DAC, and WRITE_OWNER access.

</td>
</tr>
<tr>
<td>
STANDARD_RIGHTS_ALL

</td>
<td>
Combines DELETE, READ_CONTROL, WRITE_DAC, WRITE_OWNER, and SYNCHRONIZE access. However, the SYNCHRONIZE value is not applicable to token objects. Thus, STANDARD_RIGHTS_ALL has a  functionally equivalent to STANDARD_RIGHTS_REQUIRED.

</td>
</tr>
<tr>
<td>
TOKEN_ADJUST_DEFAULT

</td>
<td>
Required to change the default owner, primary group, or DACL of an access token.

</td>
</tr>
<tr>
<td>
TOKEN_ADJUST_GROUPS

</td>
<td>
Required to adjust the attributes of the groups in an access token.

</td>
</tr>
<tr>
<td>
TOKEN_ADJUST_PRIVILEGES

</td>
<td>
Required to enable or disable the privileges in an access token.

</td>
</tr>
<tr>
<td>
TOKEN_ADJUST_SESSIONID

</td>
<td>
Required to adjust the session ID (SID) of an access token. The operating system grants this right to the new token only if the SE_TCB_NAME privilege is enabled in the access token of the calling thread.

</td>
</tr>
<tr>
<td>
TOKEN_ASSIGN_PRIMARY

</td>
<td>
Required to attach a primary token to a process. The operating system grants this right to the new token only if the SE_ASSIGNPRIMARYTOKEN_NAME privilege is enabled in the access token of the calling thread.

</td>
</tr>
<tr>
<td>
TOKEN_DUPLICATE

</td>
<td>
Required to duplicate an access token. Note that the given <i>ExistingTokenHandle</i> token must contain this right in order to successfully use this routine.

</td>
</tr>
<tr>
<td>
TOKEN_EXECUTE

</td>
<td>
Combines STANDARD_RIGHTS_EXECUTE and TOKEN_IMPERSONATE.

</td>
</tr>
<tr>
<td>
TOKEN_IMPERSONATE

</td>
<td>
Required to attach an impersonation access token to a process.

</td>
</tr>
<tr>
<td>
TOKEN_QUERY

</td>
<td>
Required to query an access token.

</td>
</tr>
<tr>
<td>
TOKEN_QUERY_SOURCE

</td>
<td>
Required to query the source of an access token.

</td>
</tr>
<tr>
<td>
TOKEN_READ

</td>
<td>
Combines STANDARD_RIGHTS_READ and TOKEN_QUERY.

</td>
</tr>
<tr>
<td>
TOKEN_WRITE

</td>
<td>
Combines STANDARD_RIGHTS_WRITE, TOKEN_ADJUST_PRIVILEGES, TOKEN_ADJUST_GROUPS, and TOKEN_ADJUST_DEFAULT.

</td>
</tr>
<tr>
<td>
TOKEN_ALL_ACCESS

</td>
<td>
Combines all possible token access permissions for a token.

</td>
</tr>
</table>
 

For additional information, see <a href="http://go.microsoft.com/fwlink/p/?linkid=91036">Access Rights for Access-Token Objects</a> in the Microsoft Windows SDK. Note that access tokens do not support the SYNCHRONIZE right.


### -param ObjectAttributes [in]

Pointer to an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that describes the requested properties for the new token. The <i>ObjectAttributes</i> parameter is optional and can be <b>NULL</b>. If the <i>ObjectAttributes</i> parameter is <b>NULL</b> or if the <b>SecurityDescriptor</b> member of the structure pointed to by the <i>ObjectAttributes</i> parameter is <b>NULL</b>, the new token receives a default security descriptor and the new token handle cannot be inherited. In that case, this default security descriptor is created from the user group, primary group, and DACL information that is stored in the caller's token.

When the <i>TokenType</i> parameter is set to <b>TokenImpersonation</b>:

<ul>
<li>
The <i>ObjectAttributes </i>parameter may be used to specify the impersonation level of the new token. This can be accomplished by setting <i>ObjectAttributes</i>-&gt;SecurityQualityOfService.ImpersonationLevel to an appropriate <a href="..\wudfddi\ne-wudfddi-_security_impersonation_level.md">SECURITY_IMPERSONATION_LEVEL</a> enumeration value. For more information, see <a href="http://go.microsoft.com/fwlink/p/?linkid=91038">SECURITY_QUALITY_OF_SERVICE</a> in the Microsoft Windows SDK documentation.

</li>
<li>
If the existing token is an impersonation token and the <i>ObjectAttributes</i> parameter provides no impersonation information, the new token's impersonation level is set to the existing token's impersonation level.

</li>
<li>
If the existing token is a primary token and no impersonation level information is provided, the new impersonation token will have a <a href="..\wudfddi\ne-wudfddi-_security_impersonation_level.md">SECURITY_IMPERSONATION_LEVEL</a> impersonation level.

</li>
</ul>

### -param EffectiveOnly [in]

A Boolean value that indicates whether the entire existing token should be duplicated into the new token or just the effective (currently enabled) part of the token. If set to <b>TRUE</b>, only the currently enabled parts of the source token will be duplicated. If set to <b>FALSE</b>, the entire existing token will be duplicated. This provides a means for a caller of a protected subsystem to limit which optional groups and privileges are made available to the protected subsystem. For example, if <i>EffectiveOnly</i> is <b>TRUE</b>, the caller could duplicate a token but remove the Administrators group and the SeTcbPrivilege right. The resulting token could then be passed to a child process (<a href="http://go.microsoft.com/fwlink/p/?linkid=91041">CreateProcessAsUser</a>), which would restrict what the child process can do. This parameter is required.


### -param TokenType [in]

Specifies one of the following values from the <a href="..\ntifs\ne-ntifs-_token_type.md">TOKEN_TYPE</a> enumeration.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>TokenPrimary</b>

</td>
<td>
The new token is a primary token. If the existing token is an impersonation token, the existing impersonation token must have an impersonation level (as provided by the <i>ObjectAttributes</i> parameter) of <b>SecurityImpersonation</b> or <b>SecurityDelegation</b>. Otherwise, <b>ZwDuplicateToken</b> returns STATUS_BAD_IMPERSONATION_LEVEL is returned.

</td>
</tr>
<tr>
<td>
<b>TokenImpersonation</b>

</td>
<td>
The new token is an impersonation token. If the existing token is an impersonation token, the requested impersonation level (as provided by the <i>ObjectAttributes</i> parameter) of the new token must not be greater than the impersonation level of the existing token. Otherwise, <b>ZwDuplicateToken </b>returns STATUS_BAD_IMPERSONATION_LEVEL.

</td>
</tr>
</table>
 

The <i>TokenType</i> parameter is required and cannot be <b>NULL</b>.


### -param NewTokenHandle [out]

A pointer to a caller-allocated variable, of type HANDLE, that receives a handle to the new token. This parameter is required and cannot be <b>NULL</b>.


## -returns



<b>ZwDuplicateToken</b> returns STATUS_SUCCESS if the call is successfull. Possible error return codes include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_VIOLATION</b></dt>
</dl>
</td>
<td width="60%">
A memory access violation occurred. For example, if the previous mode was user-mode and invalid user-mode memory was provided, <b>ZwDuplicateToken</b> returns STATUS_ACCESS_VIOLATION. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Sufficient memory could not be allocated to duplicate the new token. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BAD_IMPERSONATION_LEVEL</b></dt>
</dl>
</td>
<td width="60%">
The requested impersonation level for the new token is greater than the impersonation level of the existing token. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
<b>ZwDuplicateToken</b> returns STATUS_ACCESS_DENIED if it couldn't access <i>ExistingTokenHandle</i>. This would occur if the existing token does not have the TOKEN_DUPLICATE access right. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
<b>ZwDuplicateToken</b> returns STATUS_INVALID_HANDLE if <i>ExistingTokenHandle</i> refers to an invalid handle. 

</td>
</tr>
</table>
 




## -remarks



If no impersonation level information was provided by the <i>ObjectAttributes</i> parameter, the existing token's impersonation level will be used for the new token.

With regard to the structure pointed to by the optional <i>ObjectAttributes</i> parameter, the <b>SecurityQualityOfService</b> member of <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> points to a structure of type <b>SECURITY_QUALITY_OF_SERVICE</b>. See <a href="http://go.microsoft.com/fwlink/p/?linkid=91038">SECURITY_QUALITY_OF_SERVICE</a> in the Microsoft Windows SDK documentation for information on the members of this structure.

<div class="alert"><b>Note</b>    The <b>SecurityQualityOfService</b> member must be set <u>after</u> calling the <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> macro because <b>InitializeObjectAttributes</b> currently sets <b>SecurityQualityOfService</b> to <b>NULL</b>.</div>
<div> </div>
For information on the user-mode analog of <b>ZwDuplicateToken</b>, see <a href="http://go.microsoft.com/fwlink/p/?linkid=91047">DuplicateTokenEx</a> in the Windows SDK documentation.

When you have finished using the new token, call the <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a> function to close the token handle.

<div class="alert"><b>Note</b>  If the call to the <b>ZwDuplicateToken</b> function occurs in user mode, you should use the name "<b>NtDuplicateToken</b>" instead of "<b>ZwDuplicateToken</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="..\wudfddi\ne-wudfddi-_security_impersonation_level.md">SECURITY_IMPERSONATION_LEVEL</a>



<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>



<a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwDuplicateToken function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

