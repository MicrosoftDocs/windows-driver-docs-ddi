---
UID: NF:fltkernel.FltUninitializeFileLock
title: FltUninitializeFileLock function
author: windows-driver-content
description: The FltUninitializeFileLock routine uninitializes a FILE_LOCK structure.
old-location: ifsk\fltuninitializefilelock.htm
old-project: ifsk
ms.assetid: 15f0a4f4-70f3-4a26-92a2-728e363205f3
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_p_to_z_ad1332a2-5434-423c-91d6-de939e1cb28a.xml, FltUninitializeFileLock, FltUninitializeFileLock routine [Installable File System Drivers], fltkernel/FltUninitializeFileLock, ifsk.fltuninitializefilelock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows XP SP2, Microsoft Windows Server 2003 SP1, and later.
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
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltUninitializeFileLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltUninitializeFileLock function


## -description


The <b>FltUninitializeFileLock</b> routine uninitializes a FILE_LOCK structure.


## -parameters




### -param FileLock [in]

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541743">FltAllocateFileLock</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff543273">FltInitializeFileLock</a>.


## -returns



None




## -remarks



<b>FltUninitializeFileLock</b> uninitializes an initialized FILE_LOCK structure, freeing all file locks and completing any outstanding lock operations. The uninitialized FILE_LOCK structure can be initialized for reuse by a subsequent call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543273">FltInitializeFileLock</a>.

<b>FltUninitializeFileLock</b> can be used to uninitialize a FILE_LOCK structure allocated by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541743">FltAllocateFileLock</a>. Do not use <b>FltUninitializeFileLock</b> for such a FILE_LOCK structure unless the structure is to be initialized for reuse. It is a programming error to call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542969">FltFreeFileLock</a> for an uninitialized FILE_LOCK structure.

To allocate and initialize a new file lock structure, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541743">FltAllocateFileLock</a>. 

To free an initialized FILE_LOCK structure, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542969">FltFreeFileLock</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541743">FltAllocateFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541834">FltCheckLockForReadAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541837">FltCheckLockForWriteAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542969">FltFreeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543273">FltInitializeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543427">FltProcessFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547313">FsRtlUninitializeFileLock</a>
 

 

