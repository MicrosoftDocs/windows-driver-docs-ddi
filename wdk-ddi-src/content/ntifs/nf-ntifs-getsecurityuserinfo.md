---
UID: NF:ntifs.GetSecurityUserInfo
title: GetSecurityUserInfo function
author: windows-driver-content
description: The GetSecurityUserInfo function retrieves information about a logon session.
old-location: ifsk\getsecurityuserinfo.htm
old-project: ifsk
ms.assetid: 2f26ff14-dd2c-4e80-aea5-38a7dd16d904
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: GetSecurityUserInfo function [Installable File System Drivers], GetSecurityUserInfo, ntifs/GetSecurityUserInfo, ifsk.getsecurityuserinfo, IFSMiscRef_e375e4a8-9702-41b8-b848-0dcbc0a7d9bd.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ksecdd.lib
-	ksecdd.dll
apiname:
-	GetSecurityUserInfo
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# GetSecurityUserInfo function


## -description


The <b>GetSecurityUserInfo</b> function retrieves information about a logon <a href="http://go.microsoft.com/fwlink/p/?linkid=121237">session</a>.


## -syntax


````
NTSTATUS GetSecurityUserInfo(
  _In_opt_ PLUID             LogonId,
  _In_     ULONG             Flags,
  _Out_    PSecurityUserData *UserInformation
);
````


## -parameters




#### - LogonId [in, optional]

An optional pointer to an <a href="http://go.microsoft.com/fwlink/p/?linkid=121236">LUID</a> containing the logon session for which information is to be retrieved. If <i>LogonId</i> is <b>NULL</b>, information for the logon session of the calling thread is returned.


#### - Flags [in]

This parameter is currently not used.


#### - UserInformation [out]

A pointer to a location which contains a pointer to a <a href="http://go.microsoft.com/fwlink/p/?linkid=121238">SecurityUserData</a> structure. If the function call succeeds, the user information is returned in this structure. The caller is responsible for freeing this buffer by calling the <a href="http://go.microsoft.com/fwlink/p/?linkid=121239">LsaFreeReturnBuffer</a> function.


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


This function obtains information about a logon <a href="http://go.microsoft.com/fwlink/p/?linkid=121237">session</a> via  the <a href="http://go.microsoft.com/fwlink/p/?linkid=121238">SecurityUserData</a>  structure.



## -see-also

<a href="..\ntifs\nf-ntifs-mapsecurityerror.md">MapSecurityError</a>

<a href="http://go.microsoft.com/fwlink/p/?linkid=121239">LsaFreeReturnBuffer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20GetSecurityUserInfo function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

