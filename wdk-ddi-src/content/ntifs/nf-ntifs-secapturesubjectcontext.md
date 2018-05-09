---
UID: NF:ntifs.SeCaptureSubjectContext
title: SeCaptureSubjectContext function
author: windows-driver-content
description: The SeCaptureSubjectContext routine captures the security context of the calling thread for access validation and auditing.
old-location: ifsk\secapturesubjectcontext.htm
old-project: ifsk
ms.assetid: 7d41263e-a5f7-455e-859b-10a452a22ddf
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: SeCaptureSubjectContext, SeCaptureSubjectContext routine [Installable File System Drivers], ifsk.secapturesubjectcontext, ntifs/SeCaptureSubjectContext, seref_192d13d7-4841-4c3e-831f-c12fe3cde04f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, Wdm.h
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
-	SeCaptureSubjectContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# SeCaptureSubjectContext function


## -description


The <b>SeCaptureSubjectContext</b> routine captures the security context of the calling thread for access validation and auditing.


## -parameters




### -param SubjectContext [out]

Pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff563714">SECURITY_SUBJECT_CONTEXT</a> structure.


## -returns



None




## -remarks



The <b>SeCaptureSubjectContext</b> routine returns a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563714">SECURITY_SUBJECT_CONTEXT</a> structure, which contains references to access tokens. The contents of that structure can change. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff556675">SeLockSubjectContext</a> routine locks the primary access token and any impersonation tokens associated with the structure.



When using routines that query token information, such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff556688">SeQueryAuthenticationIdToken</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff556698">SeQuerySubjectContextToken</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff556690">SeQueryInformationToken</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff556686">SePrivilegeCheck</a>, more than once in the same security context, lock the subject context with <a href="https://msdn.microsoft.com/library/windows/hardware/ff556675">SeLockSubjectContext</a> to obtain consistent results.

File systems must call <b>SeCaptureSubjectContext</b> before performing access validation or generating audit messages. This is necessary to provide a consistent security context to routines such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff556688">SeQueryAuthenticationIdToken</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff556698">SeQuerySubjectContextToken</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff556686">SePrivilegeCheck</a>. After these operations have been performed, the captured context should be released as soon as possible by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff556704">SeReleaseSubjectContext</a>.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563714">SECURITY_SUBJECT_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556675">SeLockSubjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556686">SePrivilegeCheck</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556688">SeQueryAuthenticationIdToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556698">SeQuerySubjectContextToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556704">SeReleaseSubjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556736">SeUnlockSubjectContext</a>
 

 

