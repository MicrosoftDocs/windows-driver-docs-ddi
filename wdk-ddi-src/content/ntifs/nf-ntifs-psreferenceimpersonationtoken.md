---
UID: NF:ntifs.PsReferenceImpersonationToken
title: PsReferenceImpersonationToken function
author: windows-driver-content
description: The PsReferenceImpersonationToken routine increments the reference count of the impersonation token for the specified thread.
old-location: ifsk\psreferenceimpersonationtoken.htm
old-project: ifsk
ms.assetid: c72f48a8-ba51-423f-9105-7d78521dcae2
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PsReferenceImpersonationToken, PsReferenceImpersonationToken routine [Installable File System Drivers], ifsk.psreferenceimpersonationtoken, ntifs/PsReferenceImpersonationToken, psref_150f4e7c-56c2-4108-b5c9-0882f9027252.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
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
-	PsReferenceImpersonationToken
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsReferenceImpersonationToken function


## -description


The <b>PsReferenceImpersonationToken</b> routine increments the reference count of the impersonation token for the specified thread.


## -parameters




### -param Thread [in, out]

Address of the thread whose impersonation token's reference count is to be incremented.


### -param CopyOnOpen [out]

Pointer to a caller-allocated Boolean variable. On return, this parameter receives <b>TRUE</b> if the token cannot be opened directly. In this case, the token must be duplicated, and the duplicate token must be used instead. If the token can be opened directly, this parameter receives <b>FALSE</b>. 


### -param EffectiveOnly [out]

Pointer to a caller-allocated Boolean variable. On return, this parameter receives <b>FALSE</b> if the thread is allowed to enable groups and privileges that are currently disabled in the client security context, <b>TRUE</b> otherwise.


### -param ImpersonationLevel [out]

Pointer to a caller-allocated SECURITY_IMPERSONATION_LEVEL variable. On return, this parameter receives a value that specifies the impersonation level at which the thread is allowed to access the token. 


## -returns



<b>PsReferenceImpersonationToken</b> returns a pointer to the impersonation token for the given thread. If the thread is not currently impersonating a client, a <b>NULL</b> pointer is returned.




## -remarks



This routine is available starting with Microsoft Windows 2000. 

If the thread is currently impersonating a client, <b>PsReferenceImpersonationToken</b> increments the reference count of the impersonation token and returns a pointer to the token. If the returned pointer is non-<b>NULL</b>, the impersonation token's reference count must be decremented by calling one of the following functions:

<ul>
<li>
<b>ObDereferenceObject</b>, for Windows 2000.

</li>
<li>
<b>PsDereferenceImpersonationToken</b>, for Microsoft Windows XP or later.

</li>
</ul>
For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551893">PsDereferenceImpersonationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551907">PsImpersonateClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556631">SECURITY_IMPERSONATION_LEVEL</a>
 

 

