---
UID: NF:fltkernel.FltCheckLockForWriteAccess
title: FltCheckLockForWriteAccess function
author: windows-driver-content
description: The FltCheckLockForWriteAccess routine determines whether the caller has write access to a locked byte range of a file.
old-location: ifsk\fltchecklockforwriteaccess.htm
old-project: ifsk
ms.assetid: a98cbb3c-d2cb-4a60-8c5f-c637790db916
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_a_to_d_c9957537-90d0-4830-bba1-1043f450c367.xml, FltCheckLockForWriteAccess, FltCheckLockForWriteAccess routine [Installable File System Drivers], fltkernel/FltCheckLockForWriteAccess, ifsk.fltchecklockforwriteaccess
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	FltMgr.lib
-	FltMgr.dll
apiname:
-	FltCheckLockForWriteAccess
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltCheckLockForWriteAccess function


## -description


The <b>FltCheckLockForWriteAccess</b> routine determines whether the caller has write access to a locked byte range of a file.


## -syntax


````
BOOLEAN FltCheckLockForWriteAccess(
  _In_ PFILE_LOCK         FileLock,
  _In_ PFLT_CALLBACK_DATA CallbackData
);
````


## -parameters




### -param FileLock [in]

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="..\fltkernel\nf-fltkernel-fltallocatefilelock.md">FltAllocateFileLock</a> or <a href="..\fltkernel\nf-fltkernel-fltinitializefilelock.md">FltInitializeFileLock</a>.


### -param CallbackData [in]

Pointer to the callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a> operation. 


## -returns



<b>FltCheckLockForWriteAccess</b> returns <b>TRUE</b> if the process has write access, <b>FALSE</b> otherwise.




## -remarks



This routine is available on Microsoft Windows XP SP2, Microsoft Windows Server 2003 SP1, and later. 

<b>FltCheckLockForWriteAccess</b> checks whether the caller has write access to the entire byte range indicated in the callback data structure. 

<b>FltCheckLockForWriteAccess</b> does not complete the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a> operation.

To allocate and initialize a new file lock structure, call <a href="..\fltkernel\nf-fltkernel-fltallocatefilelock.md">FltAllocateFileLock</a>. 

To free an initialized FILE_LOCK structure, call <a href="..\fltkernel\nf-fltkernel-fltfreefilelock.md">FltFreeFileLock</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltinitializefilelock.md">FltInitializeFileLock</a>



<a href="..\fltkernel\nf-fltkernel-fltprocessfilelock.md">FltProcessFileLock</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>



<a href="..\fltkernel\nf-fltkernel-fltfreefilelock.md">FltFreeFileLock</a>



<a href="..\fltkernel\nf-fltkernel-fltchecklockforreadaccess.md">FltCheckLockForReadAccess</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlchecklockforwriteaccess~r1.md">FsRtlCheckLockForWriteAccess</a>



<a href="..\fltkernel\nf-fltkernel-fltallocatefilelock.md">FltAllocateFileLock</a>



<a href="..\fltkernel\nf-fltkernel-fltuninitializefilelock.md">FltUninitializeFileLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCheckLockForWriteAccess routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

