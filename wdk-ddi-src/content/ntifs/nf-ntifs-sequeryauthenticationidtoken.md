---
UID: NF:ntifs.SeQueryAuthenticationIdToken
title: SeQueryAuthenticationIdToken function
author: windows-driver-content
description: The SeQueryAuthenticationIdToken routine retrieves the authentication ID of an access token.
old-location: ifsk\sequeryauthenticationidtoken.htm
old-project: ifsk
ms.assetid: 4679415f-63d2-48b5-a6d4-edc54e8b3b0c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: SeQueryAuthenticationIdToken, SeQueryAuthenticationIdToken routine [Installable File System Drivers], ifsk.sequeryauthenticationidtoken, ntifs/SeQueryAuthenticationIdToken, seref_cc55425d-99c0-4fbe-a7ce-06d75ae74586.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
-	SeQueryAuthenticationIdToken
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SeQueryAuthenticationIdToken function


## -description


The <b>SeQueryAuthenticationIdToken</b> routine retrieves the authentication ID of an access token.


## -parameters




### -param Token [in]

Pointer to an access token.


### -param AuthenticationId [out]

Authentication ID of the access token. (An Authentication ID is the locally unique identifier, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>, that is assigned to the logon session that the access token represents. There can be many tokens representing a single logon session.) 


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
The call to <b>SeQueryAuthenticationIdToken</b> succeeded.

</td>
</tr>
</table>
 




## -remarks



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551893">PsDereferenceImpersonationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551896">PsDereferencePrimaryToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556690">SeQueryInformationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556698">SeQuerySubjectContextToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556720">SeTokenIsAdmin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556724">SeTokenIsRestricted</a>
 

 

