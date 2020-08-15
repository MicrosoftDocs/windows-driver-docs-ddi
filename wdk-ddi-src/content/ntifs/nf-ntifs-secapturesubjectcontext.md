---
UID: NF:ntifs.SeCaptureSubjectContext
title: SeCaptureSubjectContext function (ntifs.h)
description: The SeCaptureSubjectContext routine captures the security context of the calling thread for access validation and auditing.
old-location: ifsk\secapturesubjectcontext.htm
tech.root: ifsk
ms.assetid: 7d41263e-a5f7-455e-859b-10a452a22ddf
ms.date: 04/16/2018
keywords: ["SeCaptureSubjectContext function"]
ms.keywords: SeCaptureSubjectContext, SeCaptureSubjectContext routine [Installable File System Drivers], ifsk.secapturesubjectcontext, ntifs/SeCaptureSubjectContext, seref_192d13d7-4841-4c3e-831f-c12fe3cde04f.xml
f1_keywords:
 - "ntifs/SeCaptureSubjectContext"
 - "SeCaptureSubjectContext"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- SeCaptureSubjectContext
targetos: Windows
req.typenames: 
---

# SeCaptureSubjectContext function


## -description


The <b>SeCaptureSubjectContext</b> routine captures the security context of the calling thread for access validation and auditing.


## -parameters




### -param SubjectContext 
[out]
Pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">SECURITY_SUBJECT_CONTEXT</a> structure.


## -remarks



The <b>SeCaptureSubjectContext</b> routine returns a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">SECURITY_SUBJECT_CONTEXT</a> structure, which contains references to access tokens. The contents of that structure can change. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-selocksubjectcontext">SeLockSubjectContext</a> routine locks the primary access token and any impersonation tokens associated with the structure.



When using routines that query token information, such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequeryauthenticationidtoken">SeQueryAuthenticationIdToken</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequerysubjectcontexttoken">SeQuerySubjectContextToken</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequeryinformationtoken">SeQueryInformationToken</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seprivilegecheck">SePrivilegeCheck</a>, more than once in the same security context, lock the subject context with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-selocksubjectcontext">SeLockSubjectContext</a> to obtain consistent results.

File systems must call <b>SeCaptureSubjectContext</b> before performing access validation or generating audit messages. This is necessary to provide a consistent security context to routines such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequeryauthenticationidtoken">SeQueryAuthenticationIdToken</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequerysubjectcontexttoken">SeQuerySubjectContextToken</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seprivilegecheck">SePrivilegeCheck</a>. After these operations have been performed, the captured context should be released as soon as possible by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sereleasesubjectcontext">SeReleaseSubjectContext</a>.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">SECURITY_SUBJECT_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-selocksubjectcontext">SeLockSubjectContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seprivilegecheck">SePrivilegeCheck</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequeryauthenticationidtoken">SeQueryAuthenticationIdToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequerysubjectcontexttoken">SeQuerySubjectContextToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sereleasesubjectcontext">SeReleaseSubjectContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seunlocksubjectcontext">SeUnlockSubjectContext</a>
 

 

