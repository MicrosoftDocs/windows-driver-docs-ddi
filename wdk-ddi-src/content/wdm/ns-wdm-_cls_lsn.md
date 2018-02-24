---
UID: NS:wdm._CLS_LSN
title: "_CLS_LSN"
author: windows-driver-content
description: The CLFS_LSN structure identifies an individual record in a Common Log File System (CLFS) stream.
old-location: kernel\clfs_lsn.htm
old-project: kernel
ms.assetid: ac50c4e1-4b87-4c6e-a5c7-24f961224134
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: CLFS_LSN, kstruct_a_25e68bfe-85ad-4716-a47f-7f248ca068e4.xml, wdm/PPCLFS_LSN, CLS_LSN structure [Kernel-Mode Driver Architecture], PCLFS_LSN structure pointer [Kernel-Mode Driver Architecture], PCLFS_LSN structure [Kernel-Mode Driver Architecture], PPCLFS_LSN, PPCLFS_LSN structure pointer [Kernel-Mode Driver Architecture], wdm/PPCLS_LSN, wdm/PCLFS_LSN, *PCLFS_LSN, PCLS_LSN structure pointer [Kernel-Mode Driver Architecture], wdm/PCLS_LSN, PPCLS_LSN, _CLS_LSN, PPCLS_LSN structure pointer [Kernel-Mode Driver Architecture], *PCLS_LSN, PCLS_LSN, kernel.clfs_lsn, PCLFS_LSN, CLS_LSN, wdm/CLS_LSN
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	CLS_LSN
product: Windows
targetos: Windows
req.typenames: PPCLS_LSN, *PCLS_LSN, CLS_LSN
req.product: Windows 10 or later.
---

# _CLS_LSN structure


## -description


The <b>CLFS_LSN</b> structure identifies an individual record in a Common Log File System (CLFS) stream.


## -syntax


````
typedef struct _CLS_LSN {
  ULONGLONG Internal;
} CLS_LSN, *PCLS_LSN, **PPCLS_LSN, PCLFS_LSN, *PCLFS_LSN, **PPCLFS_LSN;
````


## -struct-fields




### -field Internal

A 64-bit value that holds three pieces of information about a log record: container identifier, block offset, and record sequence number. 


## -remarks



A container is a contiguous physical disk extent that serves as part of a CLFS log. A given CLFS log has several containers. Each container has several sector-aligned blocks, each of which holds a numbered sequence of records. A record can be identified by the triple (logical container identifier, block offset, record sequence number).

To obtain the container identifier, block offset, and record sequence number from a <b>CLFS_LSN</b> structure, call <a href="..\wdm\nf-wdm-clfslsncontainer.md">ClfsLsnContainer</a>, <a href="..\wdm\nf-wdm-clfslsnblockoffset.md">ClfsLsnBlockOffset</a>, and <a href="..\wdm\nf-wdm-clfslsnrecordsequence.md">ClfsLsnRecordSequence</a>.



