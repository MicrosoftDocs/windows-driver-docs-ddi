---
UID: NF:wdm.ClfsDeleteLogFile
title: ClfsDeleteLogFile function
author: windows-driver-content
description: The ClfsDeleteLogFile routine marks a CLFS stream for deletion.
old-location: kernel\clfsdeletelogfile.htm
old-project: kernel
ms.assetid: a8c90199-e938-45bb-9356-48591e127eed
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, ClfsDeleteLogFile, ClfsDeleteLogFile routine [Kernel-Mode Driver Architecture], Clfs_0b23f7ac-c175-4eaf-b6c9-9b23b6ebe7e3.xml, D, F, L, e, f, g, i, kernel.clfsdeletelogfile, l, o, s, t, wdm/ClfsDeleteLogFile"
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
-	ClfsDeleteLogFile
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsDeleteLogFile function


## -description


The <b>ClfsDeleteLogFile</b> routine marks a CLFS stream for deletion.


## -syntax


````
NTSTATUS ClfsDeleteLogFile(
  _In_     PUNICODE_STRING puszLogFileName,
  _In_opt_ PVOID           psdLogFile,
  _In_     ULONG           fLogOptionFlag,
  _In_opt_ PVOID           pvContext,
  _In_     ULONG           cbContext
);
````


## -parameters




### -param puszLogFileName [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that supplies the name of the CLFS stream to be deleted. 

If the stream to be deleted is the only stream of a dedicated log, the name has the form log:<i>physical log name</i>, where <i>physical log name</i> is the path name of the physical log on the underlying file system.

If the stream to be deleted is one of the streams of a multiplexed log, the name has the form log:<i>physical log name</i>::<i>stream name</i>, where <i>physical log name</i> is the path name of  the physical log on the underlying file system and <i>stream name</i> is the unique name of the stream to be deleted.


### -param pvReserved

TBD


### -param fLogOptionFlag [in]

A value that indicates the relationship between CLFS and the component that is deleting the log. For a list of possible values, see the description of the <i>fLogOptionFlag</i> parameter of the <b>ClfsCreateLogFile</b> routine.


### -param pvContext [in, optional]

A pointer to a context. The way the context is interpreted depends on the value passed in <i>fLogOptionFlag</i>.


### -param cbContext [in]

The size, in bytes, of the context pointed to by <i>pvContex</i>t. If <i>pvContext</i> is not <b>NULL</b>, this parameter must be greater than zero.


#### - psdLogFile [in, optional]

A pointer to a <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> structure that supplies the security attributes for accessing the stream. This parameter can be <b>NULL</b>.


## -returns



<b>ClfsDeleteLogFile</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



The Common Log File System (CLFS) uses the LOG_FILE_OBJECT structure to represent logs. The <a href="..\wdm\nf-wdm-clfscreatelogfile.md">ClfsCreateLogFile</a> function returns a pointer to LOG_FILE_OBJECT, which clients then pass to other CLFS functions.

CLFS clients do not directly access the members of a LOG_FILE_OBJECT structure. For information about the members, see <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a>.



<b>ClfsDeleteLogFile</b> marks a stream for deletion but does not close any log file objects that are currently open. To close a log file object, call <a href="..\wdm\nf-wdm-clfscloselogfileobject.md">ClfsCloseLogFileObject</a>. A stream marked for deletion is deleted after all log file objects associated with the stream are closed.

A CLFS stream marked for deletion will refuse subsequent requests to open the stream.

The name of a physical CLFS log does not include the .blf extension.

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 




## -see-also

<a href="..\wdm\nf-wdm-clfscloseandresetlogfile.md">ClfsCloseAndResetLogFile</a>



<a href="..\wdm\nf-wdm-clfscreatelogfile.md">ClfsCreateLogFile</a>



<a href="..\wdm\nf-wdm-clfsdeletelogbypointer.md">ClfsDeleteLogByPointer</a>



<a href="..\wdm\nf-wdm-clfscloselogfileobject.md">ClfsCloseLogFileObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsDeleteLogFile routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

