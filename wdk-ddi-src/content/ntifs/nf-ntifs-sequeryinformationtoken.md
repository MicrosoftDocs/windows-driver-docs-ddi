---
UID: NF:ntifs.SeQueryInformationToken
title: SeQueryInformationToken function
author: windows-driver-content
description: The SeQueryInformationToken routine retrieves a specified type of information about an access token. The calling process must have appropriate access rights to obtain the information.
old-location: ifsk\sequeryinformationtoken.htm
old-project: ifsk
ms.assetid: 97e28b53-8b4c-4f76-b6bb-21dad2233463
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: SeQueryInformationToken, SeQueryInformationToken routine [Installable File System Drivers], ifsk.sequeryinformationtoken, ntifs/SeQueryInformationToken, seref_80e09bda-ef06-4a25-ab50-d405f5539759.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later versions of the operating system.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	SeQueryInformationToken
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SeQueryInformationToken function


## -description


The <b>SeQueryInformationToken</b> routine retrieves a specified type of information about an access token. The calling process must have appropriate access rights to obtain the information. 


## -parameters




### -param Token [in]

A pointer to an access token from which information is to be retrieved. If <i>TokenInformationClass</i> is set to <i>TokenSource</i>, the handle must have TOKEN_QUERY_SOURCE access. For all other <i>TokenInformationClass</i> values, the handle must have TOKEN_QUERY access. 


### -param TokenInformationClass [in]

A value from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556838">TOKEN_INFORMATION_CLASS</a> enumerated type that identifies the type of information to be retrieved. 


### -param TokenInformation [out]

If STATUS_SUCCESS is returned, 
	  <i>TokenInformation</i> receives a pointer to a 
	  location that contains the address of a buffer that holds the requested 
	  information. The format of this information buffer depends upon the 
	  value of <i>TokenInformationClass</i>, as shown in 
	  the following table.  Be aware that the buffer is allocated by 
	  <b>SeQueryInformationToken</b> 
	  from paged pool. This buffer must eventually be freed by the caller by 
	  using either 
	  <a href="https://msdn.microsoft.com/library/windows/hardware/ff544590">ExFreePool</a>.
	  

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
<b>TokenDefaultDacl</b>

</td>
<td>
The buffer receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff556831">TOKEN_DEFAULT_DACL</a> structure that contains the default DACL for newly created objects. 

</td>
</tr>
<tr>
<td>
<b>TokenGroups</b>

</td>
<td>
The buffer receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff556834">TOKEN_GROUPS</a> structure that contains the group accounts associated with the token.

</td>
</tr>
<tr>
<td>
<b>TokenImpersonationLevel</b>

</td>
<td>
The buffer receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff556631">SECURITY_IMPERSONATION_LEVEL</a> value which indicates the impersonation level of the token. If the access token is not an impersonation token, the call to <b>SeQueryInformationToken</b> fails. 

</td>
</tr>
<tr>
<td>
<b>TokenOwner</b>

</td>
<td>
The buffer receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff556842">TOKEN_OWNER</a> structure that contains the default owner security identifier (<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>) for newly created objects.

</td>
</tr>
<tr>
<td>
<b>TokenPrimaryGroup</b>

</td>
<td>
The buffer receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff556845">TOKEN_PRIMARY_GROUP</a> structure that contains the default primary group SID for newly created objects. 

</td>
</tr>
<tr>
<td>
<b>TokenPrivileges</b>

</td>
<td>
The buffer receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff556846">TOKEN_PRIVILEGES</a> structure that contains the token's privileges.

</td>
</tr>
<tr>
<td>
<b>TokenSessionId</b>

</td>
<td>
The buffer receives a <b>DWORD</b> value (not a pointer to it) that indicates the Terminal Services session identifier that is associated with the token. If the token is associated with the Terminal Server console session, the session identifier is zero. A nonzero session identifier indicates a Terminal Services client session. In a non-Terminal Services environment, the session identifier is zero.

</td>
</tr>
<tr>
<td>
<b>TokenSource</b>

</td>
<td>
The buffer receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff556848">TOKEN_SOURCE</a> structure that contains the source of the token. TOKEN_QUERY_SOURCE access is needed to retrieve this information.

</td>
</tr>
<tr>
<td>
<b>TokenStatistics</b>

</td>
<td>
The buffer receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff556849">TOKEN_STATISTICS</a> structure that contains various token statistics.

</td>
</tr>
<tr>
<td>
<b>TokenType</b>

</td>
<td>
The buffer receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff556851">TOKEN_TYPE</a> value that indicates whether the token is a primary or impersonation token. 

</td>
</tr>
<tr>
<td>
<b>TokenUser</b>

</td>
<td>
The buffer receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff556855">TOKEN_USER</a> structure that contains the token's user account. 

</td>
</tr>
<tr>
<td>
<b>TokenIntegrityLevel</b>

</td>
<td>
The buffer receives a <b>DWORD</b> value (not a pointer to it) that specifies the token’s integrity level. 

</td>
</tr>
</table>
 


## -returns



<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff556690">SeQueryInformationToken</a> succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_INFO_CLASS</b></dt>
</dl>
</td>
<td width="60%">
An invalid value was supplied for <i>TokenInformationClass</i>. 

</td>
</tr>
</table>
 




## -remarks



For more information about security and access control, see the documentation about these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551893">PsDereferenceImpersonationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551896">PsDereferencePrimaryToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556631">SECURITY_IMPERSONATION_LEVEL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556688">SeQueryAuthenticationIdToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556698">SeQuerySubjectContextToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556720">SeTokenIsAdmin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556724">SeTokenIsRestricted</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556831">TOKEN_DEFAULT_DACL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556834">TOKEN_GROUPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556838">TOKEN_INFORMATION_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556842">TOKEN_OWNER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556845">TOKEN_PRIMARY_GROUP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556846">TOKEN_PRIVILEGES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556848">TOKEN_SOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556849">TOKEN_STATISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556851">TOKEN_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556855">TOKEN_USER</a>
 

 

