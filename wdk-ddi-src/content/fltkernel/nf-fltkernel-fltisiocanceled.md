---
UID: NF:fltkernel.FltIsIoCanceled
title: FltIsIoCanceled function (fltkernel.h)
description: The FltIsIoCanceled routine checks if an IRP-based operation has been canceled.
old-location: ifsk\fltisiocanceled.htm
tech.root: ifsk
ms.assetid: a27ec86b-85b3-4d65-a77a-fb6292b935d0
ms.date: 04/16/2018
keywords: ["FltIsIoCanceled function"]
ms.keywords: FltApiRef_e_to_o_00dccf3a-3f69-4c6c-b5c6-1d7371e4afbc.xml, FltIsIoCanceled, FltIsIoCanceled routine [Installable File System Drivers], fltkernel/FltIsIoCanceled, ifsk.fltisiocanceled
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
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - FltIsIoCanceled
 - fltkernel/FltIsIoCanceled
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltIsIoCanceled
---

# FltIsIoCanceled function


## -description

The <b>FltIsIoCanceled</b> routine checks if an IRP-based operation has been canceled.

## -parameters

### -param CallbackData 

[in]
Pointer to the callback data structure for the operation (<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>).

## -returns

<b>FltIsIoCanceled</b> returns <b>TRUE</b> if an IRP-based operation has been canceled and <b>FALSE</b> if the operation has not been canceled or if it is not an IRP-based operation.

## -remarks

It is a programming error to call <b>FltIsIoCanceled</b> for an operation that is not IRP-based. To determine whether the operation is IRP-based, use the <a href="/previous-versions/ff544654(v=vs.85)">FLT_IS_IRP_OPERATION</a> macro.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="/previous-versions/ff544654(v=vs.85)">FLT_IS_IRP_OPERATION</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcancelfileopen">FltCancelFileOpen</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcancelio">FltCancelIo</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltclearcancelcompletion">FltClearCancelCompletion</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetcancelcompletion">FltSetCancelCompletion</a>