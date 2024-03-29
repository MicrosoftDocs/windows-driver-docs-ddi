---
UID: NF:fltkernel.FltUninitializeOplock
title: FltUninitializeOplock function (fltkernel.h)
description: FltUninitializeOplock uninitializes an opportunistic lock (oplock) pointer.
old-location: ifsk\fltuninitializeoplock.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltUninitializeOplock function"]
ms.keywords: FltApiRef_p_to_z_d759e280-7507-44ae-8155-578320562c8b.xml, FltUninitializeOplock, FltUninitializeOplock function [Installable File System Drivers], fltkernel/FltUninitializeOplock, ifsk.fltuninitializeoplock
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltUninitializeOplock
 - fltkernel/FltUninitializeOplock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltUninitializeOplock
---

# FltUninitializeOplock function


## -description

<b>FltUninitializeOplock</b> uninitializes an opportunistic lock (oplock) pointer.

## -parameters

### -param Oplock [in]


Opaque oplock pointer. This pointer must have been initialized by a previous call to <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinitializeoplock">FltInitializeOplock</a>.

## -returns

None

## -remarks

Minifilter drivers call <b>FltUninitializeOplock</b> to uninitialize an initialized opportunistic lock (oplock) pointer. The uninitialized oplock pointer can be initialized for reuse by calling <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinitializeoplock">FltInitializeOplock</a>. 

For detailed information about opportunistic locks, see the Microsoft Windows SDK documentation.

## -see-also

<a href="/windows-hardware/drivers/ifs/fsctl-opbatch-ack-close-pending">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="/windows-hardware/drivers/ifs/fsctl-oplock-break-acknowledge">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="/windows-hardware/drivers/ifs/fsctl-oplock-break-ack-no-2">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="/windows-hardware/drivers/ifs/fsctl-oplock-break-notify">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="/windows-hardware/drivers/ifs/fsctl-request-batch-oplock">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="/windows-hardware/drivers/ifs/fsctl-request-filter-oplock">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="/windows-hardware/drivers/ifs/fsctl-request-oplock-level-1">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="/windows-hardware/drivers/ifs/fsctl-request-oplock-level-2">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcheckoplock">FltCheckOplock</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcurrentbatchoplock">FltCurrentBatchOplock</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinitializeoplock">FltInitializeOplock</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltoplockfsctrl">FltOplockFsctrl</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltoplockisfastiopossible">FltOplockIsFastIoPossible</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializeoplock">FsRtlUninitializeOplock</a>
