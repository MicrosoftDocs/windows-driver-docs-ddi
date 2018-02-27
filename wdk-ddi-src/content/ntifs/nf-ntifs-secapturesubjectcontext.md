---
UID: NF:ntifs.SeCaptureSubjectContext
title: SeCaptureSubjectContext function
author: windows-driver-content
description: The SeCaptureSubjectContext routine captures the security context of the calling thread for access validation and auditing.
old-location: ifsk\secapturesubjectcontext.htm
old-project: ifsk
ms.assetid: 7d41263e-a5f7-455e-859b-10a452a22ddf
ms.author: windowsdriverdev
ms.date: 2/16/2018
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	SeCaptureSubjectContext
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SeCaptureSubjectContext function


## -description


The <b>SeCaptureSubjectContext</b> routine captures the security context of the calling thread for access validation and auditing.


## -syntax


````
VOID SeCaptureSubjectContext(
  _Out_ PSECURITY_SUBJECT_CONTEXT SubjectContext
);
````


## -parameters




### -param SubjectContext [out]

Pointer to a caller-allocated <a href="..\wdm\ns-wdm-_security_subject_context.md">SECURITY_SUBJECT_CONTEXT</a> structure.


## -returns



None




## -remarks



The <b>SeCaptureSubjectContext</b> routine returns a pointer to a <a href="..\wdm\ns-wdm-_security_subject_context.md">SECURITY_SUBJECT_CONTEXT</a> structure, which contains references to access tokens. The contents of that structure can change. The <a href="..\wdm\nf-wdm-selocksubjectcontext.md">SeLockSubjectContext</a> routine locks the primary access token and any impersonation tokens associated with the structure.



When using routines that query token information, such as <a href="..\ntifs\nf-ntifs-sequeryauthenticationidtoken.md">SeQueryAuthenticationIdToken</a>, <a href="..\ntifs\nf-ntifs-sequerysubjectcontexttoken.md">SeQuerySubjectContextToken</a>, <a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>, and <a href="..\ntifs\nf-ntifs-seprivilegecheck.md">SePrivilegeCheck</a>, more than once in the same security context, lock the subject context with <a href="..\wdm\nf-wdm-selocksubjectcontext.md">SeLockSubjectContext</a> to obtain consistent results.

File systems must call <b>SeCaptureSubjectContext</b> before performing access validation or generating audit messages. This is necessary to provide a consistent security context to routines such as <a href="..\ntifs\nf-ntifs-sequeryauthenticationidtoken.md">SeQueryAuthenticationIdToken</a>, <a href="..\ntifs\nf-ntifs-sequerysubjectcontexttoken.md">SeQuerySubjectContextToken</a>, and <a href="..\ntifs\nf-ntifs-seprivilegecheck.md">SePrivilegeCheck</a>. After these operations have been performed, the captured context should be released as soon as possible by calling <a href="..\wdm\nf-wdm-sereleasesubjectcontext.md">SeReleaseSubjectContext</a>.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also

<a href="..\ntifs\nf-ntifs-sequeryauthenticationidtoken.md">SeQueryAuthenticationIdToken</a>



<a href="..\ntifs\nf-ntifs-sequerysubjectcontexttoken.md">SeQuerySubjectContextToken</a>



<a href="..\wdm\nf-wdm-sereleasesubjectcontext.md">SeReleaseSubjectContext</a>



<a href="..\wdm\ns-wdm-_security_subject_context.md">SECURITY_SUBJECT_CONTEXT</a>



<a href="..\ntifs\nf-ntifs-seprivilegecheck.md">SePrivilegeCheck</a>



<a href="..\wdm\nf-wdm-seunlocksubjectcontext.md">SeUnlockSubjectContext</a>



<a href="..\wdm\nf-wdm-selocksubjectcontext.md">SeLockSubjectContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeCaptureSubjectContext routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

