---
UID: NF:fltkernel.FltCheckLockForReadAccess
title: FltCheckLockForReadAccess function
author: windows-driver-content
description: The FltCheckLockForReadAccess routine determines whether the caller has read access to a locked byte range of a file.
old-location: ifsk\fltchecklockforreadaccess.htm
old-project: ifsk
ms.assetid: 18920aaa-ae43-48ec-a06d-69ccaf75ebd8
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_a_to_d_24bd7e02-fdc4-44a3-8d1a-1bb164d26769.xml, FltCheckLockForReadAccess, FltCheckLockForReadAccess routine [Installable File System Drivers], fltkernel/FltCheckLockForReadAccess, ifsk.fltchecklockforreadaccess
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	FltCheckLockForReadAccess
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltCheckLockForReadAccess function


## -description


The <b>FltCheckLockForReadAccess</b> routine determines whether the caller has read access to a locked byte range of a file.


## -parameters




### -param FileLock [in]

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541743">FltAllocateFileLock</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff543273">FltInitializeFileLock</a>.


### -param CallbackData [in]

Pointer to the callback data (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>) structure for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a> operation. 


## -returns



<b>FltCheckLockForReadAccess</b> returns <b>TRUE</b> if the process has read access, <b>FALSE</b> otherwise.




## -remarks



This routine is available on Microsoft Windows XP SP2, Microsoft Windows Server 2003 SP1, and later. 

<b>FltCheckLockForReadAccess</b> checks whether the caller has read access to the entire byte range indicated in the callback data structure. 

<b>FltCheckLockForReadAccess</b> does not complete the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a> operation. 

To allocate and initialize a new file lock structure, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541743">FltAllocateFileLock</a>. 

To free an initialized FILE_LOCK structure, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542969">FltFreeFileLock</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541743">FltAllocateFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541837">FltCheckLockForWriteAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542969">FltFreeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543273">FltInitializeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543427">FltProcessFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544595">FltUninitializeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545758">FsRtlCheckLockForReadAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>
 

 

