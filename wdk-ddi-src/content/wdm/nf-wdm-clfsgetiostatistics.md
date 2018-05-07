---
UID: NF:wdm.ClfsGetIoStatistics
title: ClfsGetIoStatistics function
author: windows-driver-content
description: The ClfsGetIoStatistics routine returns I/O statistics for a specified CLFS log.
old-location: kernel\clfsgetiostatistics.htm
old-project: kernel
ms.assetid: 68c04751-761c-4e32-927d-aad61813cd38
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: ClfsGetIoStatistics, ClfsGetIoStatistics routine [Kernel-Mode Driver Architecture], Clfs_af9b22c3-0845-4687-9a76-b6872d2b138d.xml, kernel.clfsgetiostatistics, wdm/ClfsGetIoStatistics
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
-	ClfsGetIoStatistics
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

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554316">LOG_FILE_OBJECT</a> structure that represents a CLFS stream. The I/O statistics will be collected for the stream's underlying log on stable storage. The caller previously obtained this pointer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff540792">ClfsCreateLogFile</a>.


### -param pvStatsBuffer [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541794">CLFS_IO_STATISTICS</a> structure that receives the I/O statistics data.


### -param cbStatsBuffer [in]

The size, in bytes, of the buffer pointed to by <i>pvStatsBuffer</i>. This parameter must be at least <b>sizeof</b>(<a href="https://msdn.microsoft.com/library/windows/hardware/ff541798">CLFS_IO_STATISTICS_HEADER</a>). If this parameter is less than <b>sizeof</b>(<b>CLFS_IO_STATISTICS</b>), <i>pvStatsBuffer</i> will receive only a portion of the available I/O statistics.


### -param eStatsClass [in]

This parameter is reserved for future use.


### -param pcbStatsWritten [out, optional]

A pointer to a ULONG-typed variable that receives the number of bytes actually written to <i>pvStatsBuffer</i>. This parameter can be <b>NULL</b>.


## -returns



<b>ClfsGetIoStatistics</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540792">ClfsCreateLogFile</a>
 

 

