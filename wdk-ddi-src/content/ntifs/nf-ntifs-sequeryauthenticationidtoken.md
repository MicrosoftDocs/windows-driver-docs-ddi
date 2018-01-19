---
UID: NF:ntifs.SeQueryAuthenticationIdToken
title: SeQueryAuthenticationIdToken function
author: windows-driver-content
description: The SeQueryAuthenticationIdToken routine retrieves the authentication ID of an access token.
old-location: ifsk\sequeryauthenticationidtoken.htm
old-project: ifsk
ms.assetid: 4679415f-63d2-48b5-a6d4-edc54e8b3b0c
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: SeQueryAuthenticationIdToken
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
req.alt-api: SeQueryAuthenticationIdToken
req.alt-loc: NtosKrnl.exe
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
req.typenames: TOKEN_TYPE
---

# SeQueryAuthenticationIdToken function



## -description
The <b>SeQueryAuthenticationIdToken</b> routine retrieves the authentication ID of an access token.



## -syntax

````
NTSTATUS SeQueryAuthenticationIdToken(
  _In_  PACCESS_TOKEN Token,
  _Out_ PLUID         AuthenticationId
);
````


## -parameters

### -param Token [in]

Pointer to an access token.


### -param AuthenticationId [out]

Authentication ID of the access token. (An Authentication ID is the locally unique identifier, or <a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>, that is assigned to the logon session that the access token represents. There can be many tokens representing a single logon session.) 


## -returns
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The call to <b>SeQueryAuthenticationIdToken</b> succeeded.

 


## -remarks
For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.


## -see-also
<dl>
<dt>
<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-psdereferenceimpersonationtoken.md">PsDereferenceImpersonationToken</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-psdereferenceprimarytoken.md">PsDereferencePrimaryToken</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-sequerysubjectcontexttoken.md">SeQuerySubjectContextToken</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-setokenisadmin.md">SeTokenIsAdmin</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-setokenisrestricted.md">SeTokenIsRestricted</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeQueryAuthenticationIdToken routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

