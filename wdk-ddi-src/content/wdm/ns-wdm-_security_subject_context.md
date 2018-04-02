---
UID: NS:wdm._SECURITY_SUBJECT_CONTEXT
title: "_SECURITY_SUBJECT_CONTEXT"
author: windows-driver-content
description: The SECURITY_SUBJECT_CONTEXT structure is used to capture subject security context for access validation and auditing.
old-location: ifsk\security_subject_context.htm
old-project: ifsk
ms.assetid: c9879df5-38e9-4a9f-8196-8485e85b2933
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSECURITY_SUBJECT_CONTEXT, PSECURITY_SUBJECT_CONTEXT, PSECURITY_SUBJECT_CONTEXT structure pointer [Installable File System Drivers], SECURITY_SUBJECT_CONTEXT, SECURITY_SUBJECT_CONTEXT structure [Installable File System Drivers], _SECURITY_SUBJECT_CONTEXT, ifsk.security_subject_context, securitystructures_e91a762f-82dc-4319-a479-8de15bce2bfd.xml, wdm/PSECURITY_SUBJECT_CONTEXT, wdm/SECURITY_SUBJECT_CONTEXT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	SECURITY_SUBJECT_CONTEXT
product: Windows
targetos: Windows
req.typenames: SECURITY_SUBJECT_CONTEXT, *PSECURITY_SUBJECT_CONTEXT
req.product: Windows 10 or later.
---

# _SECURITY_SUBJECT_CONTEXT structure


## -description


The SECURITY_SUBJECT_CONTEXT structure is used to capture subject security context for access validation and auditing.

Drivers are not to modify the SECURITY_SUBJECT_CONTEXT structure directly. To create and manipulate this structure, use the support routines listed in the <b>See Also</b> section. 

SECURITY_SUBJECT_CONTEXT


## -struct-fields




### -field ClientToken


### -field ImpersonationLevel


### -field PrimaryToken


### -field ProcessAuditId


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538840">ACCESS_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547026">FsRtlNotifyFullChangeDirectory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556631">SECURITY_IMPERSONATION_LEVEL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563674">SeAccessCheck</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563676">SeAssignSecurity</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563679">SeAssignSecurityEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554778">SeAuditingFileOrGlobalEvents</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554792">SeCaptureSubjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556598">SeCreateClientSecurityFromSubjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556654">SeFilterToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556675">SeLockSubjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556686">SePrivilegeCheck</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556698">SeQuerySubjectContextToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556704">SeReleaseSubjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556736">SeUnlockSubjectContext</a>
 

 

