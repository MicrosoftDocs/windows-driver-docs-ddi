---
UID: NS:wdm._CLS_IO_STATISTICS
title: "_CLS_IO_STATISTICS"
author: windows-driver-content
description: The CLFS_IO_STATISTICS structure holds I/O statistics data for a Common Log File System (CLFS) log.
old-location: kernel\clfs_io_statistics.htm
old-project: kernel
ms.assetid: 054d1673-0c1a-4ceb-821a-d61bf28392cf
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PCLFS_IO_STATISTICS, *PCLS_IO_STATISTICS, CLFS_IO_STATISTICS, CLFS_IO_STATISTICS structure [Kernel-Mode Driver Architecture], CLS_IO_STATISTICS, CLS_IO_STATISTICS structure [Kernel-Mode Driver Architecture], PCLFS_IO_STATISTICS, PCLFS_IO_STATISTICS structure pointer [Kernel-Mode Driver Architecture], PCLS_IO_STATISTICS, PCLS_IO_STATISTICS structure pointer [Kernel-Mode Driver Architecture], PPCLFS_IO_STATISTICS, PPCLFS_IO_STATISTICS structure pointer [Kernel-Mode Driver Architecture], PPCLS_IO_STATISTICS, PPCLS_IO_STATISTICS structure pointer [Kernel-Mode Driver Architecture], _CLS_IO_STATISTICS, kernel.clfs_io_statistics, kstruct_a_2e43db78-8c4e-462f-ad85-8c799be2f2e3.xml, wdm/CLFS_IO_STATISTICS, wdm/CLS_IO_STATISTICS, wdm/PCLFS_IO_STATISTICS, wdm/PCLS_IO_STATISTICS, wdm/PPCLFS_IO_STATISTICS, wdm/PPCLS_IO_STATISTICS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	CLS_IO_STATISTICS
product: Windows
targetos: Windows
req.typenames: CLS_IO_STATISTICS, *PCLS_IO_STATISTICS, PPCLS_IO_STATISTICS
req.product: Windows 10 or later.
---

# _CLS_IO_STATISTICS structure


## -description


The <b>CLFS_IO_STATISTICS</b> structure holds I/O statistics data for a Common Log File System (CLFS) log. 


## -syntax


````
typedef struct _CLS_IO_STATISTICS {
  CLFS_IO_STATISTICS_HEADER hdrIoStats;
  ULONGLONG                 cFlush;
  ULONGLONG                 cbFlush;
  ULONGLONG                 cMetaFlush;
  ULONGLONG                 cbMetaFlush;
} CLS_IO_STATISTICS, *PCLS_IO_STATISTICS, **PPCLS_IO_STATISTICS, CLFS_IO_STATISTICS, *PCLFS_IO_STATISTICS, **PPCLFS_IO_STATISTICS;
````


## -struct-fields




### -field hdrIoStats

A <a href="..\wdm\ns-wdm-_cls_io_statistics_header.md">CLFS_IO_STATISTICS_HEADER</a> structure that holds header information for the set of statistics.


### -field cFlush

The number of data flushes.


### -field cbFlush

The number of bytes of data flushed.


### -field cMetaFlush

The number of metadata flushes.


### -field cbMetaFlush

The number of bytes of metadata flushed. 


## -see-also

<a href="..\wdm\nf-wdm-clfsgetiostatistics.md">ClfsGetIoStatistics</a>



<a href="..\wdm\ns-wdm-_cls_io_statistics_header.md">CLFS_IO_STATISTICS_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CLS_IO_STATISTICS structure%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

