---
UID: NF:ntifs.SeUnlockSubjectContext
title: SeUnlockSubjectContext function
author: windows-driver-content
description: The SeUnlockSubjectContext routine unlocks the tokens of a captured subject context that were locked by a call to SeLockSubjectContext.
old-location: ifsk\seunlocksubjectcontext.htm
old-project: ifsk
ms.assetid: 5b0dda8f-52de-462b-8dab-8aed86e5dc0e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: SeUnlockSubjectContext, SeUnlockSubjectContext routine [Installable File System Drivers], ifsk.seunlocksubjectcontext, ntifs/SeUnlockSubjectContext, seref_a07c19ad-03a8-403d-9844-9e85862377ab.xml
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
-	SeUnlockSubjectContext
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SeUnlockSubjectContext function


## -description


The <b>SeUnlockSubjectContext</b> routine unlocks the tokens of a captured subject context that were locked by a call to <b>SeLockSubjectContext</b>.


## -syntax


````
VOID SeUnlockSubjectContext(
  _In_ PSECURITY_SUBJECT_CONTEXT SubjectContext
);
````


## -parameters




### -param SubjectContext [in]

Pointer to a SECURITY_SUBJECT_CONTEXT structure whose tokens are to be unlocked.


## -returns



None




## -remarks



<b>SeUnlockSubjectContext</b> releases the read locks on the tokens in the captured subject context.

Each call to <b>SeLockSubjectContext</b> must be matched by a subsequent call to <b>SeUnlockSubjectContext</b>.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also

<a href="..\wdm\nf-wdm-selocksubjectcontext.md">SeLockSubjectContext</a>



<a href="..\ntifs\nf-ntifs-sequerysubjectcontexttoken.md">SeQuerySubjectContextToken</a>



<a href="..\wdm\ns-wdm-_security_subject_context.md">SECURITY_SUBJECT_CONTEXT</a>



<a href="..\wdm\nf-wdm-sereleasesubjectcontext.md">SeReleaseSubjectContext</a>



<a href="..\ntifs\nf-ntifs-seprivilegecheck.md">SePrivilegeCheck</a>



<a href="..\ntifs\nf-ntifs-sequeryauthenticationidtoken.md">SeQueryAuthenticationIdToken</a>



<a href="..\wdm\nf-wdm-secapturesubjectcontext.md">SeCaptureSubjectContext</a>



 

 


