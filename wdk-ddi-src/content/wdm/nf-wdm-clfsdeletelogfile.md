---
UID: NF:wdm.ClfsDeleteLogFile
title: ClfsDeleteLogFile function (wdm.h)
description: The ClfsDeleteLogFile routine marks a CLFS stream for deletion.
old-location: kernel\clfsdeletelogfile.htm
tech.root: kernel
ms.assetid: a8c90199-e938-45bb-9356-48591e127eed
ms.date: 04/30/2018
ms.keywords: ClfsDeleteLogFile, ClfsDeleteLogFile routine [Kernel-Mode Driver Architecture], Clfs_0b23f7ac-c175-4eaf-b6c9-9b23b6ebe7e3.xml, kernel.clfsdeletelogfile, wdm/ClfsDeleteLogFile
f1_keywords:
 - "wdm/ClfsDeleteLogFile"
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
- ClfsDeleteLogFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# ClfsDeleteLogFile function


## -description


The <b>ClfsDeleteLogFile</b> routine marks a CLFS stream for deletion.


## -parameters




### -param puszLogFileName [in]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that supplies the name of the CLFS stream to be deleted. 

If the stream to be deleted is the only stream of a dedicated log, the name has the form log:<i>physical log name</i>, where <i>physical log name</i> is the path name of the physical log on the underlying file system.

If the stream to be deleted is one of the streams of a multiplexed log, the name has the form log:<i>physical log name</i>::<i>stream name</i>, where <i>physical log name</i> is the path name of  the physical log on the underlying file system and <i>stream name</i> is the unique name of the stream to be deleted.


### -param pvReserved
Reserved.



### -param fLogOptionFlag [in]

A value that indicates the relationship between CLFS and the component that is deleting the log. For a list of possible values, see the description of the <i>fLogOptionFlag</i> parameter of the <b>ClfsCreateLogFile</b> routine.


### -param pvContext [in, optional]

A pointer to a context. The way the context is interpreted depends on the value passed in <i>fLogOptionFlag</i>.


### -param cbContext [in]

The size, in bytes, of the context pointed to by <i>pvContex</i>t. If <i>pvContext</i> is not <b>NULL</b>, this parameter must be greater than zero.


#### - psdLogFile [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a> structure that supplies the security attributes for accessing the stream. This parameter can be <b>NULL</b>.


## -returns



<b>ClfsDeleteLogFile</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



The Common Log File System (CLFS) uses the LOG_FILE_OBJECT structure to represent logs. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatelogfile">ClfsCreateLogFile</a> function returns a pointer to LOG_FILE_OBJECT, which clients then pass to other CLFS functions.

CLFS clients do not directly access the members of a LOG_FILE_OBJECT structure. For information about the members, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a>.



<b>ClfsDeleteLogFile</b> marks a stream for deletion but does not close any log file objects that are currently open. To close a log file object, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscloselogfileobject">ClfsCloseLogFileObject</a>. A stream marked for deletion is deleted after all log file objects associated with the stream are closed.

A CLFS stream marked for deletion will refuse subsequent requests to open the stream.

The name of a physical CLFS log does not include the .blf extension.

For an explanation of CLFS concepts and terminology, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscloseandresetlogfile">ClfsCloseAndResetLogFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscloselogfileobject">ClfsCloseLogFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatelogfile">ClfsCreateLogFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsdeletelogbypointer">ClfsDeleteLogByPointer</a>
 

 

