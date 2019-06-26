---
UID: NF:fltkernel.FltInitializeFileLock
title: FltInitializeFileLock function (fltkernel.h)
description: The FltInitializeFileLock routine initializes an opaque FILE_LOCK structure that the caller has allocated from paged pool.
old-location: ifsk\fltinitializefilelock.htm
tech.root: ifsk
ms.assetid: 84bfec05-9d77-433e-bec2-ad188269fc61
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_8e2110a7-bc7b-4a98-b094-c6a7a12e7900.xml, FltInitializeFileLock, FltInitializeFileLock routine [Installable File System Drivers], fltkernel/FltInitializeFileLock, ifsk.fltinitializefilelock
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
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltInitializeFileLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltInitializeFileLock function


## -description


The <b>FltInitializeFileLock</b> routine initializes an opaque <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/file-lock">FILE_LOCK</a> structure that the caller has allocated from paged pool.


## -parameters




### -param FileLock [out]

Pointer to an uninitialized <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/file-lock">FILE_LOCK</a> structure. 


## -returns



None




## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/file-lock">FILE_LOCK</a> structure is opaque: that is, its members are reserved for system use. 

Once initialized, the <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/file-lock">FILE_LOCK</a> structure can be used to lock a byte range in a file by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltprocessfilelock">FltProcessFileLock</a>.

It is a programming error to call <b>FltInitializeFileLock</b> for a <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/file-lock">FILE_LOCK</a> structure that has already been initialized by <b>FltInitializeFileLock</b> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltallocatefilelock">FltAllocateFileLock</a>, unless the structure has been uninitialized by a subsequent call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltuninitializefilelock">FltUninitializeFileLock</a>.

When the <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/file-lock">FILE_LOCK</a> structure is no longer needed, it can be uninitialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltuninitializefilelock">FltUninitializeFileLock</a>. The uninitialized <b>FILE_LOCK</b> structure can then be initialized for reuse by calling <b>FltInitializeFileLock</b>.

To allocate and initialize a new opaque <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/file-lock">FILE_LOCK</a> structure, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltallocatefilelock">FltAllocateFileLock</a>. 

To free an initialized <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/file-lock">FILE_LOCK</a> structure, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltfreefilelock">FltFreeFileLock</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/file-lock">FILE_LOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltallocatefilelock">FltAllocateFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltchecklockforreadaccess">FltCheckLockForReadAccess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltchecklockforwriteaccess">FltCheckLockForWriteAccess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltfreefilelock">FltFreeFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltprocessfilelock">FltProcessFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltuninitializefilelock">FltUninitializeFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock">FsRtlInitializeFileLock</a>
 

 

