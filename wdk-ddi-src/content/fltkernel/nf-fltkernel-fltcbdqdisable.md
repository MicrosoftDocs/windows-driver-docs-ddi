---
UID: NF:fltkernel.FltCbdqDisable
title: FltCbdqDisable function (fltkernel.h)
description: FltCbdqDisable disables a minifilter driver's callback data queue.
old-location: ifsk\fltcbdqdisable.htm
tech.root: ifsk
ms.assetid: 7024d611-533c-43d3-91cf-a678b8359793
ms.date: 04/16/2018
keywords: ["FltCbdqDisable function"]
ms.keywords: FltApiRef_a_to_d_12682977-5b03-4656-ad7b-8f37bb8da66b.xml, FltCbdqDisable, FltCbdqDisable function [Installable File System Drivers], fltkernel/FltCbdqDisable, ifsk.fltcbdqdisable
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
req.lib: 
req.dll: 
req.irql: See Remarks section.
targetos: Windows
req.typenames: 
f1_keywords:
 - FltCbdqDisable
 - fltkernel/FltCbdqDisable
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fltkernel.h
api_name:
 - FltCbdqDisable
---

# FltCbdqDisable function


## -description

<i>FltCbdqDisable</i> disables a minifilter driver's callback data queue.

## -parameters

### -param Cbdq 

[in, out]
Pointer to the callback data queue.

## -returns

None

## -remarks

<i>FltCbdqDisable</i> disables a callback data queue so that no more items can be added to it. 

Minifilter drivers can use the <b>FltCbdq</b><i>Xxx</i> routines to implement a callback data queue for IRP-based I/O operations. By using these routines, minifilter drivers can make their queues cancel-safe; the system transparently handles I/O cancellation for the minifilter drivers. 

The <b>FltCbdq</b><i>Xxx</i> routines can only be used for IRP-based I/O operations. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="/previous-versions/ff544654(v=vs.85)">FLT_IS_IRP_OPERATION</a> macro. 

A minifilter driver normally calls <i>FltCbdqDisable</i> during instance teardown or minifilter driver unload. After calling this routine, the minifilter driver should empty, or <i>drain</i>, the queue. This can be done by calling <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqremovenextio">FltCbdqRemoveNextIo</a> repeatedly until no more items remain in the queue. 

See <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqinitialize">FltCbdqInitialize</a> for details on how to create a callback data queue. Use <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqinsertio">FltCbdqInsertIo</a> to add an I/O request to the queue. Use <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqremoveio">FltCbdqRemoveIo</a> to remove a particular I/O request from the queue, or <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqremovenextio">FltCbdqRemoveNextIo</a> to remove the next available I/O request.

To reenable the queue after disabling it, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqenable">FltCbdqEnable</a>. 

If the queue is protected by a <a href="/windows-hardware/drivers/kernel/spin-locks">spin lock</a> rather than a <a href="/windows-hardware/drivers/kernel/mutex-objects">mutex object</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializeresourcelite">resource variable</a>, the caller of <i>FltCbdqDisable</i> can be running at IRQL <= DISPATCH_LEVEL. If a mutex or resource is used, the caller must be running at IRQL <= APC_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data_queue">FLT_CALLBACK_DATA_QUEUE</a>



<a href="/previous-versions/ff544654(v=vs.85)">FLT_IS_IRP_OPERATION</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqenable">FltCbdqEnable</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqinitialize">FltCbdqInitialize</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqinsertio">FltCbdqInsertIo</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqremoveio">FltCbdqRemoveIo</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqremovenextio">FltCbdqRemoveNextIo</a>