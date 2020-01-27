---
UID: NF:wdm.ClfsCloseAndResetLogFile
title: ClfsCloseAndResetLogFile function (wdm.h)
description: The ClfsCloseAndResetLogFile routine releases all references to a specified log file object and marks its associated stream for reset.
old-location: kernel\clfscloseandresetlogfile.htm
tech.root: kernel
ms.assetid: 5b52a012-1e3e-4d1f-8780-a7015b2f3c5f
ms.date: 04/30/2018
ms.keywords: ClfsCloseAndResetLogFile, ClfsCloseAndResetLogFile routine [Kernel-Mode Driver Architecture], Clfs_79ba6a07-3da2-40e8-9e7c-6b299ef55d63.xml, kernel.clfscloseandresetlogfile, wdm/ClfsCloseAndResetLogFile
f1_keywords:
 - "wdm/ClfsCloseAndResetLogFile"
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Clfs.sys
- Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
- ClfsCloseAndResetLogFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# ClfsCloseAndResetLogFile function


## -description


The <b>ClfsCloseAndResetLogFile</b> routine releases all references to a specified log file object and marks its associated stream for reset.


## -parameters




### -param plfoLog [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">LOG_FILE_OBJECT</a> structure for which references will be released. The caller previously obtained this pointer by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatelogfile">ClfsCreateLogFile</a>.


## -returns



<b>ClfsCloseAndResetLogFile</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



<b>ClfsCloseAndResetLogFile</b> releases all references, acquired by CLFS, to the specified log file object. Typically, the client will not have acquired any additional references to the log file object. However, if the client has obtained additional refereces, it is the client's responsibility to release them.

<b>ClfsCloseAndResetLogFile</b> causes the specified log file object's reference count to drop to zero, at which time the log file object is closed (that is, its memory is deallocated). The stream represented by the log file object might not be reset, however, because there could be other log file objects that represent the same stream. The stream is reset after all log file objects that represent the stream are closed (for example by calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscloselogfileobject">ClfsCloseLogFileObject</a>).

A reset stream is like a newly created stream that has never had any records written to it.

On return from this routine, <i>plfoLog</i> is invalid.

You can call <b>ClfsCloseAndResetLogFile</b> at most 124 times for a given stream.

For an explanation of CLFS concepts and terminology, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscloselogfileobject">ClfsCloseLogFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsdeletelogbypointer">ClfsDeleteLogByPointer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsdeletelogfile">ClfsDeleteLogFile</a>
 

 

