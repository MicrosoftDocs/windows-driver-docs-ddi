---
UID: NF:wdm.ClfsFlushToLsn
title: ClfsFlushToLsn function (wdm.h)
description: The ClfsFlushToLsn routine forces, to stable storage, all records that have an LSN less than or equal to a specified LSN.
tech.root: kernel
ms.date: 12/09/2022
keywords: ["ClfsFlushToLsn function"]
ms.keywords: ClfsFlushToLsn, ClfsFlushToLsn routine [Kernel-Mode Driver Architecture], Clfs_80676b51-aa14-42bf-92ae-d11cf0a694b5.xml, kernel.clfsflushtolsn, wdm/ClfsFlushToLsn
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
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
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: IRQL <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ClfsFlushToLsn
 - wdm/ClfsFlushToLsn
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Clfs.sys
 - Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
 - ClfsFlushToLsn
---

## -description

The **ClfsFlushToLsn** routine forces, to stable storage, all records that have an LSN less than or equal to a specified LSN.

## -parameters

### -param pvMarshalContext [in]

A pointer to an opaque context associated with a marshalling area. The caller previously obtained this pointer by calling [ClfsCreateMarshallingArea](/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatemarshallingarea).

### -param plsnFlush [in]

A pointer to a [**CLFS_LSN**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_lsn) structure. All records that have an LSN less than or equal to *plsnFlush* are guaranteed to be forced to stable storage. If *plsnFlush* is equal to CLFS_LSN_NULL, then all records in the marshalling area are forced to stable storage.

### -param plsnLastFlushed [out, optional]

A pointer to a **CLFS_LSN** structure that receives the LSN of the oldest record that was not flushed. This is the LSN of the record immediately following the last record flushed.

On successful return, *plsnLastFlushed* is greater than the value supplied in *plsnFlush*. However, *plsnLastFlushed* does not necessarily point to a record in the stream. For example, if all records in the stream were flushed, *plsnLastFlushed* is the LSN that will be assigned to the next record written to the stream.

## -returns

**ClfsFlushToLsn** returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.

## -remarks

For an explanation of CLFS concepts and terminology, see [Common Log File System](/windows-hardware/drivers/kernel/using-common-log-file-system).

## -see-also

[ClfsFlushBuffers](/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsflushbuffers)
