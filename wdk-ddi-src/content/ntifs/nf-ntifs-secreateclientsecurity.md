---
UID: NF:ntifs.SeCreateClientSecurity
title: SeCreateClientSecurity function
author: windows-driver-content
description: The SeCreateClientSecurity routine initializes a security client context structure with the information needed to call SeImpersonateClientEx.
old-location: ifsk\secreateclientsecurity.htm
old-project: ifsk
ms.assetid: 10aadf41-79c4-46d6-a5ae-e8b3b5f338f0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, S, SeCreateClientSecurity, SeCreateClientSecurity routine [Installable File System Drivers], a, c, e, i, ifsk.secreateclientsecurity, l, n, ntifs/SeCreateClientSecurity, r, seref_3b2ae680-788b-4ecb-b747-427f8fd3b4bf.xml, t, u, y"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	SeCreateClientSecurity
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SeCreateClientSecurity function


## -description


The <b>SeCreateClientSecurity</b> routine initializes a security client context structure with the information needed to call <b>SeImpersonateClientEx</b>.


## -syntax


````
NTSTATUS SeCreateClientSecurity(
  _In_  PETHREAD                     ClientThread,
  _In_  PSECURITY_QUALITY_OF_SERVICE ClientSecurityQos,
  _In_  BOOLEAN                      ServerIsRemote,
  _Out_ PSECURITY_CLIENT_CONTEXT     ClientContext
);
````


## -parameters




### -param ClientThread [in]

Pointer to the thread of the client to be impersonated.


### -param ClientSecurityQos [in]

Pointer to a caller-allocated SECURITY_QUALITY_OF_SERVICE structure indicating what form of impersonation is to be performed.


### -param RemoteSession

TBD


### -param ClientContext [out]

Pointer to a caller-allocated SECURITY_CLIENT_CONTEXT structure to be initialized.


#### - ServerIsRemote [in]

Set to <b>TRUE</b> if the server of the client's request is remote.


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

<a href="..\ntifs\nf-ntifs-seimpersonateclientex.md">SeImpersonateClientEx</a>



<a href="..\ntifs\nf-ntifs-sedeleteclientsecurity.md">SeDeleteClientSecurity</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeCreateClientSecurity routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

