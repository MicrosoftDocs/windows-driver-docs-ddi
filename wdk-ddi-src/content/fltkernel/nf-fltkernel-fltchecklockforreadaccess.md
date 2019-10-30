---
UID: NF:fltkernel.FltCheckLockForReadAccess
title: FltCheckLockForReadAccess function (fltkernel.h)
description: The FltCheckLockForReadAccess routine determines whether the caller has read access to a locked byte range of a file.
old-location: ifsk\fltchecklockforreadaccess.htm
tech.root: ifsk
ms.assetid: 18920aaa-ae43-48ec-a06d-69ccaf75ebd8
ms.date: 04/16/2018
ms.keywords: FltApiRef_a_to_d_24bd7e02-fdc4-44a3-8d1a-1bb164d26769.xml, FltCheckLockForReadAccess, FltCheckLockForReadAccess routine [Installable File System Drivers], fltkernel/FltCheckLockForReadAccess, ifsk.fltchecklockforreadaccess
ms.topic: function
f1_keywords:
 - "fltkernel/FltCheckLockForReadAccess"
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- FltMgr.lib
- FltMgr.dll
api_name:
- FltCheckLockForReadAccess
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

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatefilelock">FltAllocateFileLock</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinitializefilelock">FltInitializeFileLock</a>.


### -param CallbackData [in]

Pointer to the callback data (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a> operation. 


## -returns



<b>FltCheckLockForReadAccess</b> returns <b>TRUE</b> if the process has read access, <b>FALSE</b> otherwise.




## -remarks



This routine is available on Microsoft Windows XP SP2, Microsoft Windows Server 2003 SP1, and later. 

<b>FltCheckLockForReadAccess</b> checks whether the caller has read access to the entire byte range indicated in the callback data structure. 

<b>FltCheckLockForReadAccess</b> does not complete the <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a> operation. 

To allocate and initialize a new file lock structure, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatefilelock">FltAllocateFileLock</a>. 

To free an initialized FILE_LOCK structure, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreefilelock">FltFreeFileLock</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatefilelock">FltAllocateFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltchecklockforwriteaccess">FltCheckLockForWriteAccess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreefilelock">FltFreeFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinitializefilelock">FltInitializeFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltprocessfilelock">FltProcessFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltuninitializefilelock">FltUninitializeFileLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlchecklockforreadaccess">FsRtlCheckLockForReadAccess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a>
 

 

