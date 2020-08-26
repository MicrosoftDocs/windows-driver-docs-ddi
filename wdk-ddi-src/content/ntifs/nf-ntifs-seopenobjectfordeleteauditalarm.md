---
UID: NF:ntifs.SeOpenObjectForDeleteAuditAlarm
title: SeOpenObjectForDeleteAuditAlarm function (ntifs.h)
description: The SeOpenObjectForDeleteAuditAlarm routine generates audit and alarm messages when an attempt is made to open an object for deletion.
old-location: ifsk\seopenobjectfordeleteauditalarm.htm
tech.root: ifsk
ms.assetid: c7a5bcce-a19e-4938-9d7b-ce73b3ecdc86
ms.date: 04/16/2018
keywords: ["SeOpenObjectForDeleteAuditAlarm function"]
ms.keywords: SeOpenObjectForDeleteAuditAlarm, SeOpenObjectForDeleteAuditAlarm routine [Installable File System Drivers], ifsk.seopenobjectfordeleteauditalarm, ntifs/SeOpenObjectForDeleteAuditAlarm, seref_59133039-b4e5-47d9-941a-df78051d6408.xml
f1_keywords:
 - "ntifs/SeOpenObjectForDeleteAuditAlarm"
 - "SeOpenObjectForDeleteAuditAlarm"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- SeOpenObjectForDeleteAuditAlarm
targetos: Windows
req.typenames: 
---

# SeOpenObjectForDeleteAuditAlarm function


## -description


The <b>SeOpenObjectForDeleteAuditAlarm</b> routine generates audit and alarm messages when an attempt is made to open an object for deletion.


## -parameters




### -param ObjectTypeName 
[in]
Pointer to a null-terminated string specifying the type of object to which the client is requesting access. This string appears in any audit message that is generated.


### -param Object 
[in, optional]
Address of the object being opened with intent to delete. This value is needed only to enter into log messages. If the open attempt fails, the value of <i>Object</i> is ignored. Otherwise, it must be provided.


### -param AbsoluteObjectName 
[in, optional]
Pointer to a null-terminated string specifying the name of the object being opened with intent to delete. This string appears in any audit message that is generated.


### -param SecurityDescriptor 
[in]
A pointer to the security descriptor structure for the object being opened with intent to delete.


### -param AccessState 
[in]
Pointer to an access state structure containing the object's subject context, remaining desired access types, granted access types, and, optionally, a privilege set to indicate which privileges were used to permit the access.


### -param ObjectCreated 
[in]
Set to <b>TRUE</b> if the open operation causes a new object to be created, or <b>FALSE</b> if an existing object is opened.


### -param AccessGranted 
[in]
Set to <b>TRUE</b> if open access was granted based on a previous access check or privilege check, or <b>FALSE</b> if it was denied.


### -param AccessMode 
[in]
Access mode used for the access check. Either <b>UserMode</b> or <b>KernelMode</b>.


### -param GenerateOnClose 
[out]
Pointer to a flag set by the audit generation routine when <b>SeOpenObjectAuditAlarm</b> returns.  


## -remarks



<b>SeOpenObjectForDeleteAuditAlarm</b> generates any necessary audit or alarm messages when a user-mode process attempts to open an object with the intent to delete it. <b>SeOpenObjectForDeleteAuditAlarm</b> is used by file systems when the flag FILE_DELETE_ON_CLOSE is specified. No messages are generated for kernel-mode accesses.

Before calling <b>SeOpenObjectForDeleteAuditAlarm</b>, the caller must call <b>SeLockSubjectContext</b> to lock the caller's primary and impersonation tokens. After calling <b>SeOpenObjectForDeleteAuditAlarm</b>, the caller must call <b>SeUnlockSubjectContext</b> to release these tokens.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_access_state">ACCESS_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seauditingfileevents">SeAuditingFileEvents</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seauditingfileorglobalevents">SeAuditingFileOrGlobalEvents</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sedeleteobjectauditalarm">SeDeleteObjectAuditAlarm</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-selocksubjectcontext">SeLockSubjectContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seopenobjectauditalarm">SeOpenObjectAuditAlarm</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sesetaccessstategenericmapping">SeSetAccessStateGenericMapping</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seunlocksubjectcontext">SeUnlockSubjectContext</a>



<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

