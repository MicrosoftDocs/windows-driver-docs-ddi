---
UID: NC:fltkernel.PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE
title: PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE
author: windows-driver-content
description: A minifilter driver can register a routine of type PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE as the minifilter driver's CompleteLockCallbackDataRoutine callback routine for a FILE_LOCK structure.
old-location: ifsk\pflt_complete_lock_callback_data_routine.htm
old-project: ifsk
ms.assetid: 5b6fe740-22bb-4620-86a2-1e3be1f380f3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: CompleteLockCallbackDataRoutine, CompleteLockCallbackDataRoutine routine [Installable File System Drivers], FltCallbacks_a02e356c-ad01-4ae4-bfff-b753ffa0a1c3.xml, PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE, fltkernel/CompleteLockCallbackDataRoutine, ifsk.pflt_complete_lock_callback_data_routine
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with  Windows XP with SP2 or Windows Server 2003 with SP1.
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
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	fltkernel.h
api_name:
-	CompleteLockCallbackDataRoutine
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE callback


## -description


A minifilter driver can register a routine of type <b>PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE</b> as the minifilter driver's <i>CompleteLockCallbackDataRoutine</i> callback routine for a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure. 


## -parameters




### -param Context [in, optional]

Context pointer that was passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543427">FltProcessFileLock</a>. 


### -param CallbackData [in]

Pointer to the callback data (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>) structure for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a> operation that is being completed. The lock request type will be one of the following: 

IRP_MN_LOCK

IRP_MN_UNLOCK_ALL

IRP_MN_UNLOCK_ALL_BY_KEY

IRP_MN_UNLOCK_SINGLE


## -returns



This routine returns STATUS_SUCCESS or an appropriate <b>NTSTATUS</b> value. If it returns an <b>NTSTATUS</b> value that is not a success code, the file lock is removed from the file. 




## -remarks



A minifilter driver can optionally specify a routine of type <b>PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE</b> as the minifilter driver's <i>CompleteLockCallbackDataRoutine</i> routine for a byte-range file lock. To specify this routine, the minifilter driver passes a pointer to the routine as the <i>CompleteLockCallbackDataRoutine</i> parameter for <a href="https://msdn.microsoft.com/library/windows/hardware/ff541743">FltAllocateFileLock</a>. 

When completing the an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a> operation for the file lock, filter manager calls this routine, if specified, as a notification to the minifilter.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541743">FltAllocateFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541834">FltCheckLockForReadAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541837">FltCheckLockForWriteAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542969">FltFreeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543273">FltInitializeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543427">FltProcessFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544595">FltUninitializeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551951">PUNLOCK_ROUTINE</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

