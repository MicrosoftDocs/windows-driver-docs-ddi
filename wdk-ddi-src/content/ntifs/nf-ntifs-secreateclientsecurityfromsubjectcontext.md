---
UID: NF:ntifs.SeCreateClientSecurityFromSubjectContext
title: SeCreateClientSecurityFromSubjectContext function (ntifs.h)
description: The SeCreateClientSecurityFromSubjectContext routine retrieves the access token for a security subject context and uses the result to initialize a security client context with the information needed to call SeImpersonateClientEx.
old-location: ifsk\secreateclientsecurityfromsubjectcontext.htm
tech.root: ifsk
ms.assetid: 3b3b12b8-05f7-40e6-909c-b99bf18cc299
ms.date: 04/16/2018
keywords: ["SeCreateClientSecurityFromSubjectContext function"]
ms.keywords: SeCreateClientSecurityFromSubjectContext, SeCreateClientSecurityFromSubjectContext routine [Installable File System Drivers], ifsk.secreateclientsecurityfromsubjectcontext, ntifs/SeCreateClientSecurityFromSubjectContext, seref_fac27935-a941-48f6-a27b-7ca56bd1f9e2.xml
f1_keywords:
 - "ntifs/SeCreateClientSecurityFromSubjectContext"
 - "SeCreateClientSecurityFromSubjectContext"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- SeCreateClientSecurityFromSubjectContext
targetos: Windows
req.typenames: 
---

# SeCreateClientSecurityFromSubjectContext function


## -description


The <b>SeCreateClientSecurityFromSubjectContext</b> routine retrieves the access token for a security subject context and uses the result to initialize a security client context with the information needed to call <b>SeImpersonateClientEx</b>.


## -parameters




### -param SubjectContext [in]

Pointer to the security subject context of the client to be impersonated.


### -param ClientSecurityQos [in]

Pointer to a caller-allocated SECURITY_QUALITY_OF_SERVICE structure indicating what form of impersonation is to be performed.


### -param ServerIsRemote [in]

Set to <b>TRUE</b> if the server of the client's request is remote.


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



<b>SeCreateClientSecurityFromSubjectContext</b> initializes a client security context block to represent a client's security context.

If the <b>ContextTrackingMode</b> member of <i>ClientSecurityQos</i> is set to SECURITY_DYNAMIC_TRACKING and <i>ServerIsRemote</i> is set to <b>FALSE</b>, <b>SeCreateClientSecurityFromSubjectContext</b> uses a reference to the client's effective token. Otherwise, <b>SeCreateClientSecurityFromSubjectContext</b> creates a copy of the client's token.

Each call to <b>SeCreateClientSecurityFromSubjectContext</b> must be matched by a subsequent call to <b>SeDeleteClientSecurity</b>.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">SECURITY_SUBJECT_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sedeleteclientsecurity">SeDeleteClientSecurity</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seimpersonateclientex">SeImpersonateClientEx</a>
 

 

