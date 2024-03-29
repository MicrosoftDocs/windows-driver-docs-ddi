---
UID: NF:wdm.IoCancelIrp
title: IoCancelIrp function (wdm.h)
description: The IoCancelIrp routine sets the cancel bit in a given IRP and calls the cancel routine for the IRP if there is one.
old-location: kernel\iocancelirp.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IoCancelIrp function"]
ms.keywords: IoCancelIrp, IoCancelIrp routine [Kernel-Mode Driver Architecture], k104_b43eae94-7d4e-4649-b56c-498285b5033f.xml, kernel.iocancelirp, wdm/IoCancelIrp
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoCancelIrp
 - wdm/IoCancelIrp
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoCancelIrp
---

# IoCancelIrp function


## -description

The <b>IoCancelIrp</b> routine sets the cancel bit in a given IRP and calls the cancel routine for the IRP if there is one.

## -parameters

### -param Irp [in]


A pointer to the IRP to be canceled.

## -returns

<b>IoCancelIrp</b> returns <b>TRUE</b> if the IRP had a cancel routine and this routine was called. Otherwise, it returns <b>FALSE</b>. In either case, the IRP's cancel bit is set to <b>TRUE</b>. For more information, see Remarks.

## -remarks

If the IRP has a cancel routine, <b>IoCancelIrp</b> sets the cancel bit and calls the cancel routine.

If <i>Irp</i>-><b>CancelRoutine</b> is <b>NULL</b>, and therefore the IRP is not cancelable, <b>IoCancelIrp</b> sets the IRP's cancel bit and returns <b>FALSE</b>. The IRP should be canceled at a later time when it becomes cancelable.

If a driver that does not own the IRP calls <b>IoCancelIrp</b>, the results are unpredictable. The IRP might be completed with a successful status even though its cancel bit was set.

An intermediate driver should not arbitrarily call <b>IoCancelIrp</b> unless that driver created the IRP passed in the call. Otherwise, the intermediate driver might cancel an IRP that some higher-level driver is tracking for purposes of its own.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetcancelroutine">IoSetCancelRoutine</a>
