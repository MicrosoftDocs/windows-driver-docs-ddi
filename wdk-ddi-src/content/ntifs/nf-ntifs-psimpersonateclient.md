---
UID: NF:ntifs.PsImpersonateClient
title: PsImpersonateClient function
author: windows-driver-content
description: The PsImpersonateClient routine causes a server thread to impersonate a client.
old-location: ifsk\psimpersonateclient.htm
old-project: ifsk
ms.assetid: 69cc1253-07eb-43cf-abc7-5ad02ecb014d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PsImpersonateClient, PsImpersonateClient routine [Installable File System Drivers], ifsk.psimpersonateclient, ntifs/PsImpersonateClient, psref_57279501-1e5a-4113-93ea-a04825989e73.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
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
-	PsImpersonateClient
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# PsImpersonateClient function


## -description


The <b>PsImpersonateClient</b> routine causes a server thread to impersonate a client. 


## -parameters




### -param Thread [in, out]

Pointer to the server thread that is to impersonate the client. 


### -param Token [in]

Pointer to the token to be assigned as the impersonation token. This token can be a primary token or an impersonation token. Set to <b>NULL</b> to end the impersonation. 


### -param CopyOnOpen [in]

Specifies whether the token can be opened directly. Set to <b>TRUE</b> to specify that the token cannot be opened directly. In this case, the token must be duplicated, and the duplicate token used instead. Set to <b>FALSE</b> to allow the token to be opened directly. 


### -param EffectiveOnly [in]

Set to <b>FALSE</b> to allow the server to enable groups and privileges that are currently disabled in the client security context, <b>TRUE</b> otherwise.


### -param ImpersonationLevel [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff556631">SECURITY_IMPERSONATION_LEVEL</a> value that specifies the impersonation level at which the server is to access the token. 


## -returns



<b>PsImpersonateClient</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as the following: 

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
It was not possible to impersonate a client because of job restrictions.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
There was insufficient memory to complete the operation.

</td>
</tr>
</table>
 




## -remarks



<b>PsImpersonateClient</b> causes the specified server thread to impersonate the specified client. 

The server thread could already be impersonating a client when <b>PsImpersonateClient</b> is called. If this is the case, the reference count on the token representing that client is decremented. To preserve this token for later use, drivers should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff551929">PsReferenceImpersonationToken</a> before calling <b>PsImpersonateClient</b> and save the pointer that is returned by <b>PsReferenceImpersonationToken</b>. 

To end the new impersonation and return the server thread to the previous impersonation, call <b>PsImpersonateClient</b> again, passing the saved pointer for the <i>Token</i> parameter. To end all impersonations, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551941">PsRevertToSelf</a> routine.

Otherwise, to end the impersonation and return the server thread to its original security context (that is, the one represented by its primary token), call <b>PsImpersonateClient</b> again, passing a <b>NULL</b> pointer for the <i>Token</i> parameter. 

The <b>PsImpersonateClient</b> routine can fail to successfully return the server thread to the previous impersonation if the thread is already impersonating or there are job restrictions.

It is extremely unsafe to raise the privilege state of an untrusted user thread (take a user's thread and impersonate LocalSystem, for example). If an untrusted user thread had its privilege raised, the user could grab the thread token after it has been elevated and subvert the security of the entire system. 

In cases where a higher privilege state is required, the task should be dispatched to a work queue where the task can be safely handled by system worker thread . This way no impersonation is necessary.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff556659">SeImpersonateClientEx</a> routine can be used to cause a thread to impersonate a user.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559936">PsGetCurrentThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551929">PsReferenceImpersonationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551941">PsRevertToSelf</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556631">SECURITY_IMPERSONATION_LEVEL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556659">SeImpersonateClientEx</a>
 

 

