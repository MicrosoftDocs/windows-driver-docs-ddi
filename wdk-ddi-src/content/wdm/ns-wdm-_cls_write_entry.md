---
UID: NS:wdm._CLS_WRITE_ENTRY
title: "_CLS_WRITE_ENTRY"
author: windows-driver-content
description: The CLFS_WRITE_ENTRY structure holds the address and size of a buffer that contains one unit of data to be written to a Common Log File System (CLFS) stream.
old-location: kernel\clfs_write_entry.htm
old-project: kernel
ms.assetid: 4b008fc7-35fe-40f9-8475-1a2ac04edb58
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PCLFS_WRITE_ENTRY, *PCLS_WRITE_ENTRY, CLFS_WRITE_ENTRY, CLFS_WRITE_ENTRY structure [Kernel-Mode Driver Architecture], CLS_WRITE_ENTRY, CLS_WRITE_ENTRY structure [Kernel-Mode Driver Architecture], PCLFS_WRITE_ENTRY, PCLFS_WRITE_ENTRY structure pointer [Kernel-Mode Driver Architecture], PCLS_WRITE_ENTRY, PCLS_WRITE_ENTRY structure pointer [Kernel-Mode Driver Architecture], PPCLFS_WRITE_ENTRY, PPCLFS_WRITE_ENTRY structure pointer [Kernel-Mode Driver Architecture], PPCLS_WRITE_ENTRY, PPCLS_WRITE_ENTRY structure pointer [Kernel-Mode Driver Architecture], _CLS_WRITE_ENTRY, kernel.clfs_write_entry, kstruct_a_331b7685-f256-4071-8edf-e517afc2b8cc.xml, wdm/CLFS_WRITE_ENTRY, wdm/CLS_WRITE_ENTRY, wdm/PCLFS_WRITE_ENTRY, wdm/PCLS_WRITE_ENTRY, wdm/PPCLFS_WRITE_ENTRY, wdm/PPCLS_WRITE_ENTRY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	CLS_WRITE_ENTRY
product:
- Windows
targetos: Windows
req.typenames: CLS_WRITE_ENTRY, *PCLS_WRITE_ENTRY, PPCLS_WRITE_ENTRY
---

# _CLS_WRITE_ENTRY structure


## -description


The <b>CLFS_WRITE_ENTRY</b> structure holds the address and size of a buffer that contains one unit of data to be written to a Common Log File System (CLFS) stream.


## -struct-fields




### -field Buffer

A pointer to the buffer that holds the data. 


### -field ByteLength

The size, in bytes, of the buffer pointed to by <b>Buffer</b>. 


## -remarks



CLFS collects the buffers pointed to by several <b>CLFS_WRITE_ENTRY</b> structures into a single log record. The log record is then placed in a log I/O block along with other log records. Eventually the log I/O block is flushed to disk.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541723">ClfsReserveAndAppendLog</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541726">ClfsReserveAndAppendLogAligned</a>
 

 

