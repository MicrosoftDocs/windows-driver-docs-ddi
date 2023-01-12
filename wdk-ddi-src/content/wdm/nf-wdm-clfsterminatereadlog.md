---
UID: NF:wdm.ClfsTerminateReadLog
title: ClfsTerminateReadLog function (wdm.h)
description: The ClfsTerminateReadLog routine invalidates a specified read context after freeing resources associated with the context.
tech.root: kernel
ms.date: 12/09/2022
keywords: ["ClfsTerminateReadLog function"]
ms.keywords: ClfsTerminateReadLog, ClfsTerminateReadLog routine [Kernel-Mode Driver Architecture], Clfs_691e308a-56d7-498f-af11-8908cc13b1b7.xml, kernel.clfsterminatereadlog, wdm/ClfsTerminateReadLog
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
 - ClfsTerminateReadLog
 - wdm/ClfsTerminateReadLog
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Clfs.sys
 - Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
 - ClfsTerminateReadLog
---

## -description

The **ClfsTerminateReadLog** routine invalidates a specified read context after freeing resources associated with the context.

## -parameters

### -param pvCursorContext [in]

A pointer to the read context to be invalidated. The caller previously obtained this pointer by calling [ClfsReadLogRecord](/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsreadlogrecord) or [ClfsReadRestartArea](/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsreadrestartarea).

## -returns

**ClfsTerminateReadLog** returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.

## -remarks

> [!WARNING]
> Failure to call this routine can lead to memory leaks, premature exhaustion of log I/O blocks, and increased frequency of log flushes. Attempting to use *pvCursorContext* after it is freed is equivalent to accessing freed memory and can lead to unexpected behavior.

For an explanation of CLFS concepts and terminology, see [Common Log File System](/windows-hardware/drivers/kernel/using-common-log-file-system).

## -see-also

[ClfsReadLogRecord](/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsreadlogrecord)

[ClfsReadRestartArea](/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsreadrestartarea)
