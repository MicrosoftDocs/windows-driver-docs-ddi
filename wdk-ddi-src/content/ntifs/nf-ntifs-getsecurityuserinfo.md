---
UID: NF:ntifs.GetSecurityUserInfo
title: GetSecurityUserInfo function (ntifs.h)
description: The GetSecurityUserInfo function retrieves information about a logon session.
old-location: ifsk\getsecurityuserinfo.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["GetSecurityUserInfo function"]
ms.keywords: GetSecurityUserInfo, GetSecurityUserInfo function [Installable File System Drivers], IFSMiscRef_e375e4a8-9702-41b8-b848-0dcbc0a7d9bd.xml, ifsk.getsecurityuserinfo, ntifs/GetSecurityUserInfo
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000 and later.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - GetSecurityUserInfo
 - ntifs/GetSecurityUserInfo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ksecdd.lib
 - ksecdd.dll
api_name:
 - GetSecurityUserInfo
---

# GetSecurityUserInfo function


## -description

The <b>GetSecurityUserInfo</b> function retrieves information about a logon <a href="/windows/win32/secgloss/s-gly">session</a>.

## -parameters

### -param LogonId 

[in, optional]
An optional pointer to an <a href="/windows/win32/secgloss/l-gly">LUID</a> containing the logon session for which information is to be retrieved. If <i>LogonId</i> is <b>NULL</b>, information for the logon session of the calling thread is returned.

### -param Flags 

[in]
This parameter is currently not used.

### -param UserInformation 

[out]
A pointer to a location which contains a pointer to a <a href="/windows/win32/api/ntsecpkg/ns-ntsecpkg-security_user_data">SecurityUserData</a> structure. If the function call succeeds, the user information is returned in this structure. The caller is responsible for freeing this buffer by calling the <a href="/windows/win32/api/ntsecapi/nf-ntsecapi-lsafreereturnbuffer">LsaFreeReturnBuffer</a> function.

## -returns

<b>GetSecurityUserInfo</b> returns an appropriate NTSTATUS value, such as one of the following.

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
The SecurityUserData structure, indirectly pointed to by <i>UserInformation</i>, contains the requested user information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_SUCH_LOGON_SESSION</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the specified logon session does not exist.

</td>
</tr>
</table>

## -remarks

This function obtains information about a logon <a href="/windows/win32/secgloss/s-gly">session</a> via  the <a href="/windows/win32/api/ntsecpkg/ns-ntsecpkg-security_user_data">SecurityUserData</a>  structure.

## -see-also

<a href="/windows/win32/api/ntsecapi/nf-ntsecapi-lsafreereturnbuffer">LsaFreeReturnBuffer</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-mapsecurityerror">MapSecurityError</a>
