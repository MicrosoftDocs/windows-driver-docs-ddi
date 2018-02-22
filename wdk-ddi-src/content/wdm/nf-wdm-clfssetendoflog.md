---
UID: NF:wdm.ClfsSetEndOfLog
title: ClfsSetEndOfLog function
author: windows-driver-content
description: The ClfsSetEndOfLog routine truncates a CLFS stream.
old-location: kernel\clfssetendoflog.htm
old-project: kernel
ms.assetid: 7e3b2eed-2de6-4459-a125-a27d9db69c93
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ClfsSetEndOfLog, kernel.clfssetendoflog, wdm/ClfsSetEndOfLog, ClfsSetEndOfLog routine [Kernel-Mode Driver Architecture], Clfs_408fe60c-e1bb-4d39-92ab-703eefe78c5c.xml
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
-	ClfsSetEndOfLog
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsSetEndOfLog function


## -description


The <b>ClfsSetEndOfLog</b> routine truncates a CLFS stream.


## -syntax


````
NTSTATUS ClfsSetEndOfLog(
  _In_ PLOG_FILE_OBJECT plfoLog,
  _In_ PCLFS_LSN        plsnEnd
);
````


## -parameters




### -param plfoLog [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554316">LOG_FILE_OBJECT</a> structure that represents a CLFS stream. This stream must be the only stream of a dedicated log. The caller previously obtained this pointer by calling <a href="..\wdm\nf-wdm-clfscreatelogfile.md">ClfsCreateLogFile</a>.


### -param plsnEnd [in]

A pointer to a <a href="..\wdm\ns-wdm-_cls_lsn.md">CLFS_LSN</a> structure that supplies the LSN of the record that is to become the last record of the stream. This must be the exact LSN of one of the records in the stream.


## -returns



<b>ClfsSetEndOfLog</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



The LSN supplied in the <i>plsnEnd</i> value is not validated. It is the responsibility of the caller to provide a valid LSN; that is, one that is the exact LSN of a record in the stream.

This stream represented by <i>plfoLog</i> must be from a dedicated log. This routine does not support streams from multiplexed logs.

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>.

The kernel-mode routine <b>ClfsSetEndOfLog</b> is reserved for future use and currently always returns STATUS_NOT_SUPPORTED. However, the user-mode routine <b>SetEndOfLog</b> is currently supported. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554316">LOG_FILE_OBJECT</a>



<a href="..\wdm\nf-wdm-clfssetarchivetail.md">ClfsSetArchiveTail </a>



<a href="..\wdm\nf-wdm-clfssetendoflog.md">ClfsSetEndOfLog</a>



<a href="..\wdm\nf-wdm-clfsadvancelogbase.md">ClfsAdvanceLogBase</a>



<a href="..\wdm\ns-wdm-_cls_lsn.md">CLFS_LSN</a>



<a href="..\wdm\nf-wdm-clfscreatelogfile.md">ClfsCreateLogFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsSetEndOfLog routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

