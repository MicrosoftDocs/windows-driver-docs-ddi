---
UID: NF:wdm.ClfsCloseLogFileObject
title: ClfsCloseLogFileObject function
author: windows-driver-content
description: The ClfsCloseLogFileObject routine releases all references to a log file object.
old-location: kernel\clfscloselogfileobject.htm
old-project: kernel
ms.assetid: 0ebb82bd-b8f2-469b-90a9-5c1773f7b58a
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: ClfsCloseLogFileObject, ClfsCloseLogFileObject routine [Kernel-Mode Driver Architecture], Clfs_836288b2-fd9b-4855-acfd-ad12d7e25b19.xml, kernel.clfscloselogfileobject, wdm/ClfsCloseLogFileObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
-	ClfsCloseLogFileObject
product: Windows
targetos: Windows
req.typenames: 
---

# ClfsCloseLogFileObject function


## -description


The <b>ClfsCloseLogFileObject</b> routine releases all references to a log file object.


## -parameters




### -param plfoLog [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554316">LOG_FILE_OBJECT</a> structure for which references will be released.The caller previously obtained this pointer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff540792">ClfsCreateLogFile</a>.


## -returns



<b>ClfsCloseLogFileObject</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



ClfsCloseLogFileObject releases all references, acquired by CLFS, to the specified log file object. Typically, the client will not have acquired any additional references to the log file object. However, if the client has obtained additional refereces, it is the client's responsibility to release them.

ClfsCloseLogFileObject causes the specified log file object's reference count to drop to zero, at which time the log file object is closed (that is, its memory is deallocated). The stream represented by the log file object might remain open, however, because there could be other log file objects that represent the same stream. The stream is closed after all log file objects that represent the stream are closed.

On return from this routine, <i>plfoLog</i> is invalid.

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540787">ClfsCloseAndResetLogFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540792">ClfsCreateLogFile</a>
 

 

