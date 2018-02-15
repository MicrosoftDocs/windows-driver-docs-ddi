---
UID: NF:fltkernel.FltAllocateFileLock
title: FltAllocateFileLock function
author: windows-driver-content
description: The FltAllocateFileLock routine allocates and initializes a new FILE_LOCK structure.
old-location: ifsk\fltallocatefilelock.htm
old-project: ifsk
ms.assetid: f5a96fc2-e6b8-44df-a827-d10d693f6f2b
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: ifsk.fltallocatefilelock, fltkernel/FltAllocateFileLock, FltAllocateFileLock, FltApiRef_a_to_d_f59cead3-059a-4457-9339-c90cc007ca63.xml, FltAllocateFileLock routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	FltMgr.lib
-	FltMgr.dll
apiname:
-	FltAllocateFileLock
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltAllocateFileLock function


## -description


The <b>FltAllocateFileLock</b> routine allocates and initializes a new <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure. 


## -syntax


````
PFILE_LOCK FltAllocateFileLock(
  _In_opt_ PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE CompleteLockCallbackDataRoutine,
  _In_opt_ PUNLOCK_ROUTINE                          UnlockRoutine
);
````


## -parameters




### -param CompleteLockCallbackDataRoutine [in, optional]

Pointer to a <a href="..\fltkernel\nc-fltkernel-pflt_complete_lock_callback_data_routine.md">PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE</a>-typed callback routine to be called when an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a> request is completed. This parameter is optional and can be <b>NULL</b>. 


### -param UnlockRoutine [in, optional]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551951">PUNLOCK_ROUTINE</a>-typed callback routine to be called when the byte range is unlocked. This parameter is optional and can be <b>NULL</b>. 


## -returns



<b>FltAllocateFileLock</b> returns a pointer to the newly allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure. 




## -remarks



<b>FltAllocateFileLock</b> allocates a new <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure from paged pool and initializes it.

The returned <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure can be used to lock a byte range in a file by calling <a href="..\fltkernel\nf-fltkernel-fltprocessfilelock.md">FltProcessFileLock</a>. 

When the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure is no longer needed, it can be uninitialized by calling <a href="..\fltkernel\nf-fltkernel-fltuninitializefilelock.md">FltUninitializeFileLock</a>. The uninitialized <b>FILE_LOCK</b> structure can then be initialized for reuse by calling <b>FltInitializeFileLock</b>. 

To free an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure, call <a href="..\fltkernel\nf-fltkernel-fltfreefilelock.md">FltFreeFileLock</a>. 

When the <i>CallbackData</i> parameter passed to <a href="..\fltkernel\nf-fltkernel-fltprocessfilelock.md">FltProcessFileLock</a> represents a fast I/O operation, the callback specified in <i>CompleteLockCallbackDataRoutine</i> is not invoked. Only when the I/O operation in <i>CallbackData</i> is an IRP, and <i>CompleteLockCallbackDataRoutine</i> is not NULL, will the callback routine be called.




## -see-also

<a href="..\fltkernel\nc-fltkernel-pflt_complete_lock_callback_data_routine.md">PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a>



<a href="..\fltkernel\nf-fltkernel-fltfreefilelock.md">FltFreeFileLock</a>



<a href="..\fltkernel\nf-fltkernel-fltuninitializefilelock.md">FltUninitializeFileLock</a>



<a href="..\fltkernel\nf-fltkernel-fltchecklockforwriteaccess.md">FltCheckLockForWriteAccess</a>



<a href="..\fltkernel\nf-fltkernel-fltinitializefilelock.md">FltInitializeFileLock</a>



<a href="..\fltkernel\nf-fltkernel-fltchecklockforreadaccess.md">FltCheckLockForReadAccess</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock~r1.md">FsRtlAllocateFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a>



<a href="..\fltkernel\nf-fltkernel-fltprocessfilelock.md">FltProcessFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551951">PUNLOCK_ROUTINE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltAllocateFileLock routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

