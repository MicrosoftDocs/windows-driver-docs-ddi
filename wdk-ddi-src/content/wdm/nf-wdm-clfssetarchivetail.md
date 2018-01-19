---
UID: NF:wdm.ClfsSetArchiveTail
title: ClfsSetArchiveTail function
author: windows-driver-content
description: The ClfsSetArchiveTail routine sets the archive tail of a CLFS log to a specified LSN.
old-location: kernel\clfssetarchivetail.htm
old-project: kernel
ms.assetid: 58c1d222-72c5-4b40-9ae5-f633bac599f0
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ClfsSetArchiveTail
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
req.alt-api: ClfsSetArchiveTail
req.alt-loc: Clfs.sys,Ext-MS-Win-fs-clfs-l1-1-0.dll
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsSetArchiveTail function



## -description
The <b>ClfsSetArchiveTail</b> routine sets the archive tail of a CLFS log to a specified LSN.



## -syntax

````
NTSTATUS ClfsSetArchiveTail(
  _In_ PLOG_FILE_OBJECT plfoLog,
  _In_ PCLFS_LSN        plsnArchiveTail
);
````


## -parameters

### -param plfoLog [in]

A pointer to a <a href="..\wdm\ns-wdm-_file_object.md">LOG_FILE_OBJECT</a> structure that represents a CLFS log. The caller previously obtained this pointer by calling <a href="..\wdm\nf-wdm-clfscreatelogfile.md">ClfsCreateLogFile</a>.


### -param plsnArchiveTail [in]

A pointer to a <a href="..\wdm\ns-wdm-_cls_lsn.md">CLFS_LSN</a> structure that specifies the LSN that is to become the new archive tail. This must be the exact LSN of a record in the log.


## -returns
<b>ClfsSetArchiveTail</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.


## -remarks
The <i>plsnArchiveTail</i> value specifies where archiving starts in the log. The next archiving will start at <u>or before</u> this LSN.

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 


## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_file_object.md">LOG_FILE_OBJECT</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-clfscreatelogfile.md">ClfsCreateLogFile</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-clfsadvancelogbase.md">ClfsAdvanceLogBase</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-clfssetendoflog.md">ClfsSetEndOfLog </a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsSetArchiveTail routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

