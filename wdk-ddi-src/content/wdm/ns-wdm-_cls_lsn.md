---
UID: NS:wdm._CLS_LSN
title: _CLS_LSN (wdm.h)
description: The CLFS_LSN structure identifies an individual record in a Common Log File System (CLFS) stream.
old-location: kernel\clfs_lsn.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["CLS_LSN structure"]
ms.keywords: "*PCLFS_LSN, *PCLS_LSN, CLFS_LSN, CLS_LSN, CLS_LSN structure [Kernel-Mode Driver Architecture], PCLFS_LSN, PCLFS_LSN structure [Kernel-Mode Driver Architecture], PCLFS_LSN structure pointer [Kernel-Mode Driver Architecture], PCLS_LSN, PCLS_LSN structure pointer [Kernel-Mode Driver Architecture], PPCLFS_LSN, PPCLFS_LSN structure pointer [Kernel-Mode Driver Architecture], PPCLS_LSN, PPCLS_LSN structure pointer [Kernel-Mode Driver Architecture], _CLS_LSN, kernel.clfs_lsn, kstruct_a_25e68bfe-85ad-4716-a47f-7f248ca068e4.xml, wdm/CLS_LSN, wdm/PCLFS_LSN, wdm/PCLS_LSN, wdm/PPCLFS_LSN, wdm/PPCLS_LSN"
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
targetos: Windows
req.typenames: CLS_LSN, *PCLS_LSN, PPCLS_LSN
f1_keywords:
 - _CLS_LSN
 - wdm/_CLS_LSN
 - PCLS_LSN
 - wdm/PCLS_LSN
 - CLS_LSN
 - wdm/CLS_LSN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - CLS_LSN
---

# _CLS_LSN structure


## -description

The <b>CLFS_LSN</b> structure identifies an individual record in a Common Log File System (CLFS) stream.

## -struct-fields

### -field Internal

A 64-bit value that holds three pieces of information about a log record: container identifier, block offset, and record sequence number.

## -remarks

A container is a contiguous physical disk extent that serves as part of a CLFS log. A given CLFS log has several containers. Each container has several sector-aligned blocks, each of which holds a numbered sequence of records. A record can be identified by the triple (logical container identifier, block offset, record sequence number).

To obtain the container identifier, block offset, and record sequence number from a <b>CLFS_LSN</b> structure, call <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfslsncontainer">ClfsLsnContainer</a>, <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfslsnblockoffset">ClfsLsnBlockOffset</a>, and <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfslsnrecordsequence">ClfsLsnRecordSequence</a>.
