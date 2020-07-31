---
UID: NS:wdm._CLS_IO_STATISTICS_HEADER
title: _CLS_IO_STATISTICS_HEADER (wdm.h)
description: The CLFS_IO_STATISTICS_HEADER structure holds the header portion of a CLFS_IO_STATISTICS structure.
old-location: kernel\clfs_io_statistics_header.htm
tech.root: kernel
ms.assetid: ac0da755-ea2f-4b68-947c-c314d114f273
ms.date: 04/30/2018
keywords: ["_CLS_IO_STATISTICS_HEADER structure"]
ms.keywords: "*PCLFS_IO_STATISTICS_HEADER, *PCLS_IO_STATISTICS_HEADER, CLFS_IO_STATISTICS_HEADER, CLFS_IO_STATISTICS_HEADER structure [Kernel-Mode Driver Architecture], CLS_IO_STATISTICS_HEADER, CLS_IO_STATISTICS_HEADER structure [Kernel-Mode Driver Architecture], PCLFS_IO_STATISTICS_HEADER, PCLFS_IO_STATISTICS_HEADER structure pointer [Kernel-Mode Driver Architecture], PCLS_IO_STATISTICS_HEADER, PCLS_IO_STATISTICS_HEADER structure pointer [Kernel-Mode Driver Architecture], PPCLFS_IO_STATISTICS_HEADER, PPCLFS_IO_STATISTICS_HEADER structure pointer [Kernel-Mode Driver Architecture], PPCLS_IO_STATISTICS_HEADER, PPCLS_IO_STATISTICS_HEADER structure pointer [Kernel-Mode Driver Architecture], _CLS_IO_STATISTICS_HEADER, kernel.clfs_io_statistics_header, kstruct_a_4b54b209-c331-4bbd-b217-d77594bd6e46.xml, wdm/CLFS_IO_STATISTICS_HEADER, wdm/CLS_IO_STATISTICS_HEADER, wdm/PCLFS_IO_STATISTICS_HEADER, wdm/PCLS_IO_STATISTICS_HEADER, wdm/PPCLFS_IO_STATISTICS_HEADER, wdm/PPCLS_IO_STATISTICS_HEADER"
f1_keywords:
 - "wdm/CLS_IO_STATISTICS_HEADER"
 - "CLS_IO_STATISTICS_HEADER"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- CLS_IO_STATISTICS_HEADER
targetos: Windows
req.typenames: CLS_IO_STATISTICS_HEADER, *PCLS_IO_STATISTICS_HEADER, PPCLS_IO_STATISTICS_HEADER
---

# _CLS_IO_STATISTICS_HEADER structure


## -description


The <b>CLFS_IO_STATISTICS_HEADER</b> structure holds the header portion of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_io_statistics">CLFS_IO_STATISTICS</a> structure.


## -struct-fields




### -field ubMajorVersion

The major version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_io_statistics">CLFS_IO_STATISTICS</a> structure.


### -field ubMinorVersion

The minor version of the <b>CLFS_IO_STATISTICS</b> structure.


### -field eStatsClass

Reserved for future use. This member is ignored. 


### -field cbLength

The size, in bytes, of the <b>CLFS_IO_STATISTICS</b> structure, including the header.


### -field coffData

The offset, in bytes, from the beginning of the <b>CLFS_IO_STATISTICS</b> structure to the beginning of the statistics data. This member allows for transparent modifications to the header. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_io_statistics">CLFS_IO_STATISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsgetiostatistics">ClfsGetIoStatistics</a>
 

 

