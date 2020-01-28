---
UID: NF:ntifs.ZwSetInformationToken
title: ZwSetInformationToken function (ntifs.h)
description: The ZwSetInformationToken routine modifies information in a specified token. The calling process must have appropriate access rights to set the information.
old-location: kernel\zwsetinformationtoken.htm
tech.root: kernel
ms.assetid: fdb1245c-7804-4cb9-9632-bedb9f7f7b2b
ms.date: 04/30/2018
ms.keywords: NtSetInformationToken, ZwSetInformationToken, ZwSetInformationToken routine [Kernel-Mode Driver Architecture], k111_1122461b-dab8-4a40-8f05-db62ca25763b.xml, kernel.zwsetinformationtoken, ntifs/NtSetInformationToken, ntifs/ZwSetInformationToken
f1_keywords:
 - "ntifs/ZwSetInformationToken"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwSetInformationToken
- NtSetInformationToken
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwSetInformationToken function


## -description


The <b>ZwSetInformationToken</b> routine modifies information in a specified token. The calling process must have appropriate access rights to set the information. 


## -parameters




### -param TokenHandle [in]

Handle for an access token in which information is to be modified. 


### -param TokenInformationClass [in]

A value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ne-ntifs-_token_information_class">TOKEN_INFORMATION_CLASS</a> enumerated type identifying the type of information to be modified. The possible values for this parameter are listed in the <i>TokenInformationClass</i> Value column of the table shown in the description of the <i>TokenInformation</i> parameter. 


### -param TokenInformation [in]

Pointer to a caller-supplied buffer containing the information to be modified in the token. The structure of the information in this buffer depends upon the value of <i>TokenInformationClass</i>, as shown in the following table. All structures must be aligned on a 32-bit boundary. 

<table>
<tr>
<th><i>TokenInformationClass</i> value</th>
<th>Effect on <i>TokenInformation</i> buffer</th>
</tr>
<tr>
<td>
<b>TokenDefaultDacl</b>

</td>
<td>
The buffer contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_default_dacl">TOKEN_DEFAULT_DACL</a> structure specifying the default <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_acl">DACL</a> for newly created objects. TOKEN_ADJUST_DEFAULT access is required to set this information. The buffer contents are not validated for structural correctness or consistency. 

</td>
</tr>
<tr>
<td>
<b>TokenGroups</b>

</td>
<td>
Not a valid information class. This information is read-only. 

</td>
</tr>
<tr>
<td>
<b>TokenOwner</b>

</td>
<td>
The buffer contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_owner">TOKEN_OWNER</a> structure specifying the default owner <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a> for newly created objects. TOKEN_ADJUST_DEFAULT access is required to set this information. The owner values that may be specified are restricted to the user and group IDs with an attribute indicating they can be assigned as the owner of objects. 

</td>
</tr>
<tr>
<td>
<b>TokenPrimaryGroup</b>

</td>
<td>
The buffer contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_primary_group">TOKEN_PRIMARY_GROUP</a> structure specifying the default primary group <b>SID</b> for newly created objects. TOKEN_ADJUST_DEFAULT access is required to set this information. Must be one of the group IDs already in the token. 

</td>
</tr>
<tr>
<td>
<b>TokenPrivileges</b>

</td>
<td>
Not a valid information class. This information is read-only. 

</td>
</tr>
<tr>
<td>
<b>TokenSource</b>

</td>
<td>
Not a valid information class. This information is read-only. 

</td>
</tr>
<tr>
<td>
<b>TokenStatistics</b>

</td>
<td>
Not a valid information class. This information is read-only. 

</td>
</tr>
<tr>
<td>
<b>TokenUser</b>

</td>
<td>
Not a valid information class. This information is read-only. 

</td>
</tr>
</table>
 


### -param TokenInformationLength [in]

Size, in bytes, of the structure passed in the <i>TokenInformation</i> buffer. Must be greater than or equal to the minimum value given in the following table. 

<table>
<tr>
<th><i>TokenInformationClass</i> value</th>
<th>Minimum <i>TokenInformationLength</i></th>
</tr>
<tr>
<td>
<b>TokenDefaultDacl</b>

</td>
<td>
<b>sizeof</b>(<b>TOKEN_DEFAULT_DACL</b>) 

</td>
</tr>
<tr>
<td>
<b>TokenOwner</b>

</td>
<td>
<b>sizeof</b>(<b>TOKEN_OWNER</b>) 

</td>
</tr>
<tr>
<td>
<b>TokenPrimaryGroup</b>

</td>
<td>
<b>sizeof</b>(<b>TOKEN_PRIMARY_GROUP</b>) 

</td>
</tr>
</table>
 


## -returns



<b>ZwSetInformationToken</b> returns STATUS_SUCCESS or an appropriate error status. Possible error status codes include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
<i>TokenHandle</i> did not have the required access.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ALLOTTED_SPACE_EXCEEDED</b></dt>
</dl>
</td>
<td width="60%">
The space allotted for storage of the default discretionary access control and the primary group ID is not large enough to accept the new value of one of these fields.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The value of <i>TokenInformationLength</i> was less than the required minimum.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The specified default owner's security information could not be captured.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
<i>TokenHandle</i> was not a valid handle.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_INFO_CLASS</b></dt>
</dl>
</td>
<td width="60%">
<i>TokenInformationClass</i> was not a valid token information class.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_OWNER</b></dt>
</dl>
</td>
<td width="60%">
The caller cannot set the specified ID to be an owner (or default owner) of an object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PRIMARY_GROUP</b></dt>
</dl>
</td>
<td width="60%">
The caller cannot set the specified ID to be the primary group of an object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_SID</b></dt>
</dl>
</td>
<td width="60%">
The specified default owner's security information was not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
<i>TokenHandle</i> was not a token handle.

</td>
</tr>
</table>
 




## -remarks



For more information about security and access control, see the documentation on these topics in the Windows SDK.

<div class="alert"><b>Note</b>  If the call to the <b>ZwSetInformationToken</b> function occurs in user mode, you should use the name "<a href="https://msdn.microsoft.com/library/windows/hardware/ff567102">NtSetInformationToken</a>" instead of "<b>ZwSetInformationToken</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-psdereferenceimpersonationtoken">PsDereferenceImpersonationToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-psdereferenceprimarytoken">PsDereferencePrimaryToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_security_impersonation_level">SECURITY_IMPERSONATION_LEVEL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequeryauthenticationidtoken">SeQueryAuthenticationIdToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequerysubjectcontexttoken">SeQuerySubjectContextToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-setokenisadmin">SeTokenIsAdmin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-setokenisrestricted">SeTokenIsRestricted</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_default_dacl">TOKEN_DEFAULT_DACL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_groups">TOKEN_GROUPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ne-ntifs-_token_information_class">TOKEN_INFORMATION_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_owner">TOKEN_OWNER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_primary_group">TOKEN_PRIMARY_GROUP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_privileges">TOKEN_PRIVILEGES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_source">TOKEN_SOURCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_statistics">TOKEN_STATISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ne-ntifs-_token_type">TOKEN_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_user">TOKEN_USER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567055">ZwQueryInformationToken</a>
 

 

