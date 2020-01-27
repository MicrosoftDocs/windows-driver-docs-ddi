---
UID: NF:wdm.ClfsGetIoStatistics
title: ClfsGetIoStatistics function (wdm.h)
description: The ClfsGetIoStatistics routine returns I/O statistics for a specified CLFS log.
old-location: kernel\clfsgetiostatistics.htm
tech.root: kernel
ms.assetid: 68c04751-761c-4e32-927d-aad61813cd38
ms.date: 04/30/2018
ms.keywords: ClfsGetIoStatistics, ClfsGetIoStatistics routine [Kernel-Mode Driver Architecture], Clfs_af9b22c3-0845-4687-9a76-b6872d2b138d.xml, kernel.clfsgetiostatistics, wdm/ClfsGetIoStatistics
f1_keywords:
 - "wdm/ClfsGetIoStatistics"
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
- ClfsGetIoStatistics
product:
- Windows
targetos: Windows
req.typenames: 
---

# ClfsGetIoStatistics function


## -description


The <b>ClfsGetIoStatistics</b> routine returns I/O statistics for a specified CLFS log.


## -parameters




### -param plfoLog [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">LOG_FILE_OBJECT</a> structure that represents a CLFS stream. The I/O statistics will be collected for the stream's underlying log on stable storage. The caller previously obtained this pointer by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatelogfile">ClfsCreateLogFile</a>.


### -param pvStatsBuffer [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_io_statistics">CLFS_IO_STATISTICS</a> structure that receives the I/O statistics data.


### -param cbStatsBuffer [in]

The size, in bytes, of the buffer pointed to by <i>pvStatsBuffer</i>. This parameter must be at least <b>sizeof</b>(<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_io_statistics_header">CLFS_IO_STATISTICS_HEADER</a>). If this parameter is less than <b>sizeof</b>(<b>CLFS_IO_STATISTICS</b>), <i>pvStatsBuffer</i> will receive only a portion of the available I/O statistics.


### -param eStatsClass [in]

This parameter is reserved for future use.


### -param pcbStatsWritten [out, optional]

A pointer to a ULONG-typed variable that receives the number of bytes actually written to <i>pvStatsBuffer</i>. This parameter can be <b>NULL</b>.


## -returns



<b>ClfsGetIoStatistics</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



For an explanation of CLFS concepts and terminology, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatelogfile">ClfsCreateLogFile</a>
 

 

