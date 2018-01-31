---
UID: NF:wdm.ClfsDeleteLogByPointer
title: ClfsDeleteLogByPointer function
author: windows-driver-content
description: The ClfsDeleteLogByPointer routine marks a CLFS stream for deletion.
old-location: kernel\clfsdeletelogbypointer.htm
old-project: kernel
ms.assetid: da6e4133-a2ba-4f8c-9490-e1f9b453b6e2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/ClfsDeleteLogByPointer, Clfs_d5571c5c-19a0-4113-8401-910721d76191.xml, kernel.clfsdeletelogbypointer, ClfsDeleteLogByPointer routine [Kernel-Mode Driver Architecture], ClfsDeleteLogByPointer
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
apiname:
-	ClfsDeleteLogByPointer
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsDeleteLogByPointer function


## -description


The <b>ClfsDeleteLogByPointer</b> routine marks a CLFS stream for deletion. 


## -syntax


````
NTSTATUS ClfsDeleteLogByPointer(
  _In_ PLOG_FILE_OBJECT plfoLog
);
````


## -parameters




#### - plfoLog [in]

A pointer to a <a href="..\wdm\ns-wdm-_file_object.md">LOG_FILE_OBJECT</a> structure that represents an open instance of the stream to be deleted. The caller previously obtained this pointer by calling <a href="..\wdm\nf-wdm-clfscreatelogfile.md">ClfsCreateLogFile</a>.


## -returns


<b>ClfsDeleteLogByPointer</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.



## -remarks


<b>ClfsDeleteLogByPointer</b> marks a stream for deletion but does not close the log file object pointed to by <i>plfoLog</i>. To close a log file object, call <a href="..\wdm\nf-wdm-clfscloselogfileobject.md">ClfsCloseLogFileObject</a>. A stream marked for deletion is deleted after all log file objects associated with the stream are closed.

A CLFS stream marked for deletion will refuse subsequent requests to open the stream.

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 



## -see-also

<a href="..\wdm\nf-wdm-clfscreatelogfile.md">ClfsCreateLogFile</a>

<a href="..\wdm\nf-wdm-clfsdeletelogfile.md">ClfsDeleteLogFile</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsDeleteLogByPointer routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

