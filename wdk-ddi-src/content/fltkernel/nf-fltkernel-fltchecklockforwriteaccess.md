---
UID: NF:fltkernel.FltCheckLockForWriteAccess
title: FltCheckLockForWriteAccess function (fltkernel.h)
description: The FltCheckLockForWriteAccess routine determines whether the caller has write access to a locked byte range of a file.
old-location: ifsk\fltchecklockforwriteaccess.htm
tech.root: ifsk
ms.assetid: a98cbb3c-d2cb-4a60-8c5f-c637790db916
ms.date: 04/16/2018
ms.keywords: FltApiRef_a_to_d_c9957537-90d0-4830-bba1-1043f450c367.xml, FltCheckLockForWriteAccess, FltCheckLockForWriteAccess routine [Installable File System Drivers], fltkernel/FltCheckLockForWriteAccess, ifsk.fltchecklockforwriteaccess
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
req.lib: FltMgr.lib
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltCheckLockForWriteAccess
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltCheckLockForWriteAccess function


## -description


The <b>FltCheckLockForWriteAccess</b> routine determines whether the caller has write access to a locked byte range of a file.


## -parameters




### -param FileLock [in]

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541743">FltAllocateFileLock</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff543273">FltInitializeFileLock</a>.


### -param CallbackData [in]

Pointer to the callback data (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>) structure for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a> operation. 


## -returns



<b>FltCheckLockForWriteAccess</b> returns <b>TRUE</b> if the process has write access, <b>FALSE</b> otherwise.




## -remarks



This routine is available on Microsoft Windows XP SP2, Microsoft Windows Server 2003 SP1, and later. 

<b>FltCheckLockForWriteAccess</b> checks whether the caller has write access to the entire byte range indicated in the callback data structure. 

<b>FltCheckLockForWriteAccess</b> does not complete the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a> operation.

To allocate and initialize a new file lock structure, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541743">FltAllocateFileLock</a>. 

To free an initialized FILE_LOCK structure, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542969">FltFreeFileLock</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541743">FltAllocateFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541834">FltCheckLockForReadAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542969">FltFreeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543273">FltInitializeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543427">FltProcessFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544595">FltUninitializeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545760">FsRtlCheckLockForWriteAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>
 

 

