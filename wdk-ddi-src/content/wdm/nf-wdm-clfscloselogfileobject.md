---
UID: NF:wdm.ClfsCloseLogFileObject
title: ClfsCloseLogFileObject function (wdm.h)
description: The ClfsCloseLogFileObject routine releases all references to a log file object.
old-location: kernel\clfscloselogfileobject.htm
tech.root: kernel
ms.assetid: 0ebb82bd-b8f2-469b-90a9-5c1773f7b58a
ms.date: 04/30/2018
keywords: ["ClfsCloseLogFileObject function"]
ms.keywords: ClfsCloseLogFileObject, ClfsCloseLogFileObject routine [Kernel-Mode Driver Architecture], Clfs_836288b2-fd9b-4855-acfd-ad12d7e25b19.xml, kernel.clfscloselogfileobject, wdm/ClfsCloseLogFileObject
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ClfsCloseLogFileObject
 - wdm/ClfsCloseLogFileObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Clfs.sys
 - Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
 - ClfsCloseLogFileObject
---

# ClfsCloseLogFileObject function


## -description

The <b>ClfsCloseLogFileObject</b> routine releases all references to a log file object.

## -parameters

### -param plfoLog 

[in]
A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">LOG_FILE_OBJECT</a> structure for which references will be released.The caller previously obtained this pointer by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatelogfile">ClfsCreateLogFile</a>.

## -returns

<b>ClfsCloseLogFileObject</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.

## -remarks

ClfsCloseLogFileObject releases all references, acquired by CLFS, to the specified log file object. Typically, the client will not have acquired any additional references to the log file object. However, if the client has obtained additional refereces, it is the client's responsibility to release them.

ClfsCloseLogFileObject causes the specified log file object's reference count to drop to zero, at which time the log file object is closed (that is, its memory is deallocated). The stream represented by the log file object might remain open, however, because there could be other log file objects that represent the same stream. The stream is closed after all log file objects that represent the stream are closed.

On return from this routine, <i>plfoLog</i> is invalid.

For an explanation of CLFS concepts and terminology, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscloseandresetlogfile">ClfsCloseAndResetLogFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatelogfile">ClfsCreateLogFile</a>

