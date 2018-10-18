---
UID: NF:ntifs.SeReleaseSubjectContext
title: SeReleaseSubjectContext function
author: windows-driver-content
description: The SeReleaseSubjectContext routine releases a subject security context captured by an earlier call to SeCaptureSubjectContext.
old-location: ifsk\sereleasesubjectcontext.htm
tech.root: ifsk
ms.assetid: efae077e-2698-4392-ac2a-8f41acdb12a2
ms.date: 4/16/2018
ms.keywords: SeReleaseSubjectContext, SeReleaseSubjectContext routine [Installable File System Drivers], ifsk.sereleasesubjectcontext, ntifs/SeReleaseSubjectContext, seref_f46fe5d3-13d1-4907-85b4-47eb78116fe0.xml
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
-	SeReleaseSubjectContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# SeReleaseSubjectContext function


## -description


The <b>SeReleaseSubjectContext</b> routine releases a subject security context captured by an earlier call to <b>SeCaptureSubjectContext</b>.


## -parameters




### -param SubjectContext [in, out]

Pointer to the captured security context.


## -returns



None




## -remarks



File systems must call <b>SeCaptureSubjectContext</b> before performing access validation or generating audit messages. This is necessary to provide a consistent security context to routines such as <b>SeQueryAuthenticationIdToken</b>, <b>SeQuerySubjectContextToken</b>, and <b>SePrivilegeCheck</b>. After these operations have been performed, the captured context should be released as soon as possible by calling <b>SeReleaseSubjectContext</b>.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563714">SECURITY_SUBJECT_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554792">SeCaptureSubjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556675">SeLockSubjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556686">SePrivilegeCheck</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556688">SeQueryAuthenticationIdToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556698">SeQuerySubjectContextToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556736">SeUnlockSubjectContext</a>
 

 

