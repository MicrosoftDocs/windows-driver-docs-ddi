---
UID: NF:fltkernel.FltCurrentBatchOplock
title: FltCurrentBatchOplock function (fltkernel.h)
description: A minifilter driver calls FltCurrentBatchOplock to determine whether there are any batch or filter opportunistic locks (oplocks) on a file.
old-location: ifsk\fltcurrentbatchoplock.htm
tech.root: ifsk
ms.assetid: 00eb27ee-2c6d-47c7-b3a6-63a6a7aac2fb
ms.date: 04/16/2018
ms.keywords: FltApiRef_a_to_d_7835829e-3397-47c3-bc12-c77f8d844927.xml, FltCurrentBatchOplock, FltCurrentBatchOplock function [Installable File System Drivers], fltkernel/FltCurrentBatchOplock, ifsk.fltcurrentbatchoplock
ms.topic: function
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
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- FltMgr.lib
- FltMgr.dll
api_name:
- FltCurrentBatchOplock
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltCurrentBatchOplock function


## -description


A minifilter driver calls <b>FltCurrentBatchOplock</b> to determine whether there are any batch or filter opportunistic locks (oplocks) on a file. 


## -parameters




### -param Oplock [in]

Opaque oplock pointer for the file. This pointer must have been initialized by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltinitializeoplock">FltInitializeOplock</a>. 


## -returns



<b>FltCurrentBatchOplock</b> returns <b>TRUE</b> if there are current outstanding batch or filter oplocks; <b>FALSE</b> otherwise. 




## -remarks



<b>FltCurrentBatchOplock</b> returns <b>FALSE</b> if no batch or filter opportunistic locks are currently held. 

For detailed information about opportunistic locks, see the Microsoft Windows SDK documentation. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-opbatch-ack-close-pending">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-oplock-break-acknowledge">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-oplock-break-ack-no-2">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-oplock-break-notify">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-batch-oplock">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-filter-oplock">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-oplock-level-1">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-request-oplock-level-2">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcheckoplock">FltCheckOplock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltinitializeoplock">FltInitializeOplock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltoplockfsctrl">FltOplockFsctrl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltoplockisfastiopossible">FltOplockIsFastIoPossible</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltuninitializeoplock">FltUninitializeOplock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcurrentbatchoplock">FsRtlCurrentBatchOplock</a>
 

 

