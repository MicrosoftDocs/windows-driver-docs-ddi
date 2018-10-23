---
UID: NF:ntifs.SeCreateClientSecurity
title: SeCreateClientSecurity function
author: windows-driver-content
description: The SeCreateClientSecurity routine initializes a security client context structure with the information needed to call SeImpersonateClientEx.
old-location: ifsk\secreateclientsecurity.htm
tech.root: ifsk
ms.assetid: 10aadf41-79c4-46d6-a5ae-e8b3b5f338f0
ms.date: 04/16/2018
ms.keywords: SeCreateClientSecurity, SeCreateClientSecurity routine [Installable File System Drivers], ifsk.secreateclientsecurity, ntifs/SeCreateClientSecurity, seref_3b2ae680-788b-4ecb-b747-427f8fd3b4bf.xml
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
-	SeCreateClientSecurity
product:
- Windows
targetos: Windows
req.typenames: 
---

# SeCreateClientSecurity function


## -description


The <b>SeCreateClientSecurity</b> routine initializes a security client context structure with the information needed to call <b>SeImpersonateClientEx</b>.


## -parameters




### -param ClientThread [in]

Pointer to the thread of the client to be impersonated.


### -param ClientSecurityQos [in]

Pointer to a caller-allocated SECURITY_QUALITY_OF_SERVICE structure indicating what form of impersonation is to be performed.


### -param RemoteSession

<p>Set to <b>TRUE</b> if the server of the client's request is remote.</p>


### -param ClientContext [out]

Pointer to a caller-allocated SECURITY_CLIENT_CONTEXT structure to be initialized.


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
The security client context was successfully initialized.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BAD_IMPERSONATION_LEVEL</b></dt>
</dl>
</td>
<td width="60%">
The client to be impersonated is currently impersonating a client of its own, and one of the following is true:

<ul>
<li>
The client's effective token cannot be passed on for use by another server, because its impersonation level is <b>SecurityAnonymous</b> or <b>SecurityIdentification</b>. 

</li>
<li>
<i>ServerIsRemote</i> is <b>TRUE</b>, and the client thread is impersonating its client at other than <b>SecurityDelegation</b> level.

</li>
</ul>
</td>
</tr>
</table>
 




## -remarks



<b>SeCreateClientSecurity</b> initializes a client security context block to represent a client's security context.

If the <b>ContextTrackingMode</b> member of <i>ClientSecurityQos</i> is set to SECURITY_DYNAMIC_TRACKING and <i>ServerIsRemote</i> is set to <b>FALSE</b>, <b>SeCreateClientSecurity</b> uses a reference to the client's effective token. Otherwise, <b>SeCreateClientSecurity</b> creates a copy of the client's token.

Each call to <b>SeCreateClientSecurity</b> must be matched by a subsequent call to <b>SeDeleteClientSecurity</b>.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556648">SeDeleteClientSecurity</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556659">SeImpersonateClientEx</a>
 

 

