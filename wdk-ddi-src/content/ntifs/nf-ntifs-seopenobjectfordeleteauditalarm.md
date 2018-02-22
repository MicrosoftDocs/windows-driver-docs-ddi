---
UID: NF:ntifs.SeOpenObjectForDeleteAuditAlarm
title: SeOpenObjectForDeleteAuditAlarm function
author: windows-driver-content
description: The SeOpenObjectForDeleteAuditAlarm routine generates audit and alarm messages when an attempt is made to open an object for deletion.
old-location: ifsk\seopenobjectfordeleteauditalarm.htm
old-project: ifsk
ms.assetid: c7a5bcce-a19e-4938-9d7b-ce73b3ecdc86
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ifsk.seopenobjectfordeleteauditalarm, ntifs/SeOpenObjectForDeleteAuditAlarm, SeOpenObjectForDeleteAuditAlarm, seref_59133039-b4e5-47d9-941a-df78051d6408.xml, SeOpenObjectForDeleteAuditAlarm routine [Installable File System Drivers]
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
-	SeOpenObjectForDeleteAuditAlarm
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SeOpenObjectForDeleteAuditAlarm function


## -description


The <b>SeOpenObjectForDeleteAuditAlarm</b> routine generates audit and alarm messages when an attempt is made to open an object for deletion.


## -syntax


````
VOID SeOpenObjectForDeleteAuditAlarm(
  _In_     PUNICODE_STRING      ObjectTypeName,
  _In_opt_ PVOID                Object,
  _In_opt_ PUNICODE_STRING      AbsoluteObjectName,
  _In_     PSECURITY_DESCRIPTOR SecurityDescriptor,
  _In_     PACCESS_STATE        AccessState,
  _In_     BOOLEAN              ObjectCreated,
  _In_     BOOLEAN              AccessGranted,
  _In_     KPROCESSOR_MODE      AccessMode,
  _Out_    PBOOLEAN             GenerateOnClose
);
````


## -parameters




### -param ObjectTypeName [in]

Pointer to a null-terminated string specifying the type of object to which the client is requesting access. This string appears in any audit message that is generated.


### -param Object [in, optional]

Address of the object being opened with intent to delete. This value is needed only to enter into log messages. If the open attempt fails, the value of <i>Object</i> is ignored. Otherwise, it must be provided.


### -param AbsoluteObjectName [in, optional]

Pointer to a null-terminated string specifying the name of the object being opened with intent to delete. This string appears in any audit message that is generated.


### -param SecurityDescriptor [in]

A pointer to the security descriptor structure for the object being opened with intent to delete.


### -param AccessState [in]

Pointer to an access state structure containing the object's subject context, remaining desired access types, granted access types, and, optionally, a privilege set to indicate which privileges were used to permit the access.


### -param ObjectCreated [in]

Set to <b>TRUE</b> if the open operation causes a new object to be created, or <b>FALSE</b> if an existing object is opened.


### -param AccessGranted [in]

Set to <b>TRUE</b> if open access was granted based on a previous access check or privilege check, or <b>FALSE</b> if it was denied.


### -param AccessMode [in]

Access mode used for the access check. Either <b>UserMode</b> or <b>KernelMode</b>.


### -param GenerateOnClose [out]

Pointer to a flag set by the audit generation routine when <b>SeOpenObjectAuditAlarm</b> returns.  


## -returns



None




## -remarks



<b>SeOpenObjectForDeleteAuditAlarm</b> generates any necessary audit or alarm messages when a user-mode process attempts to open an object with the intent to delete it. <b>SeOpenObjectForDeleteAuditAlarm</b> is used by file systems when the flag FILE_DELETE_ON_CLOSE is specified. No messages are generated for kernel-mode accesses.

Before calling <b>SeOpenObjectForDeleteAuditAlarm</b>, the caller must call <b>SeLockSubjectContext</b> to lock the caller's primary and impersonation tokens. After calling <b>SeOpenObjectForDeleteAuditAlarm</b>, the caller must call <b>SeUnlockSubjectContext</b> to release these tokens.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\ntifs\nf-ntifs-sedeleteobjectauditalarm.md">SeDeleteObjectAuditAlarm</a>



<a href="..\ntifs\nf-ntifs-sesetaccessstategenericmapping.md">SeSetAccessStateGenericMapping</a>



<a href="..\ntifs\nf-ntifs-selocksubjectcontext.md">SeLockSubjectContext</a>



<a href="..\ntifs\nf-ntifs-seauditingfileevents.md">SeAuditingFileEvents</a>



<a href="..\ntifs\nf-ntifs-seunlocksubjectcontext.md">SeUnlockSubjectContext</a>



<a href="..\ntifs\nf-ntifs-seauditingfileorglobalevents.md">SeAuditingFileOrGlobalEvents</a>



<a href="..\wdm\ns-wdm-_access_state.md">ACCESS_STATE</a>



<a href="..\ntifs\nf-ntifs-seopenobjectauditalarm.md">SeOpenObjectAuditAlarm</a>



<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeOpenObjectForDeleteAuditAlarm routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

