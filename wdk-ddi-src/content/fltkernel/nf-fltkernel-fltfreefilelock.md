---
UID: NF:fltkernel.FltFreeFileLock
title: FltFreeFileLock function
author: windows-driver-content
description: The FltFreeFileLock routine uninitializes and frees an initialized FILE_LOCK structure.
old-location: ifsk\fltfreefilelock.htm
old-project: ifsk
ms.assetid: bcf2ac97-0aa2-4464-a045-b98866351243
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_e_to_o_823e2511-8afe-4151-bbac-a9481c079068.xml, FltFreeFileLock, FltFreeFileLock routine [Installable File System Drivers], fltkernel/FltFreeFileLock, ifsk.fltfreefilelock
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
-	FltFreeFileLock
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltFreeFileLock function


## -description


The <b>FltFreeFileLock</b> routine uninitializes and frees an initialized FILE_LOCK structure. 


## -parameters




### -param FileLock [in]

Pointer to the FILE_LOCK structure. This structure must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541743">FltAllocateFileLock</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff543273">FltInitializeFileLock</a>.


## -returns



None




## -remarks



The FILE_LOCK structure is opaque: that is, its members are reserved for system use. 

To allocate and initialize a new file lock structure, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541743">FltAllocateFileLock</a>. 

It is a programming error to call <b>FltFreeFileLock</b> for a FILE_LOCK structure that has already been uninitialized by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff544595">FltUninitializeFileLock</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541743">FltAllocateFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541834">FltCheckLockForReadAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541837">FltCheckLockForWriteAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543273">FltInitializeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543427">FltProcessFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544595">FltUninitializeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546011">FsRtlFreeFileLock</a>
 

 

