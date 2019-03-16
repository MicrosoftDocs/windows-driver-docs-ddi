---
UID: NF:fltkernel.FltCbdqDisable
title: FltCbdqDisable function (fltkernel.h)
description: FltCbdqDisable disables a minifilter driver's callback data queue.
old-location: ifsk\fltcbdqdisable.htm
tech.root: ifsk
ms.assetid: 7024d611-533c-43d3-91cf-a678b8359793
ms.date: 04/16/2018
ms.keywords: FltApiRef_a_to_d_12682977-5b03-4656-ad7b-8f37bb8da66b.xml, FltCbdqDisable, FltCbdqDisable function [Installable File System Drivers], fltkernel/FltCbdqDisable, ifsk.fltcbdqdisable
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
req.lib: 
req.dll: 
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- fltkernel.h
api_name:
- FltCbdqDisable
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltCbdqDisable function


## -description


<i>FltCbdqDisable</i> disables a minifilter driver's callback data queue. 


## -parameters




### -param Cbdq [in, out]

Pointer to the callback data queue. 


## -returns



None 




## -remarks



<i>FltCbdqDisable</i> disables a callback data queue so that no more items can be added to it. 

Minifilter drivers can use the <b>FltCbdq</b><i>Xxx</i> routines to implement a callback data queue for IRP-based I/O operations. By using these routines, minifilter drivers can make their queues cancel-safe; the system transparently handles I/O cancellation for the minifilter drivers. 

The <b>FltCbdq</b><i>Xxx</i> routines can only be used for IRP-based I/O operations. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. 

A minifilter driver normally calls <i>FltCbdqDisable</i> during instance teardown or minifilter driver unload. After calling this routine, the minifilter driver should empty, or <i>drain</i>, the queue. This can be done by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541825">FltCbdqRemoveNextIo</a> repeatedly until no more items remain in the queue. 

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541802">FltCbdqInitialize</a> for details on how to create a callback data queue. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff541815">FltCbdqInsertIo</a> to add an I/O request to the queue. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff541821">FltCbdqRemoveIo</a> to remove a particular I/O request from the queue, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541825">FltCbdqRemoveNextIo</a> to remove the next available I/O request.

To reenable the queue after disabling it, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541799">FltCbdqEnable</a>. 

If the queue is protected by a <a href="https://msdn.microsoft.com/0585fc2a-0d0b-434d-92b3-da07a9385444">spin lock</a> rather than a <a href="https://msdn.microsoft.com/e2142b6d-f460-4f80-be0f-e00b5d43731c">mutex object</a> or <a href="https://msdn.microsoft.com/be18a6e6-863d-4a0c-9bcd-a36ace0b54fe">resource variable</a>, the caller of <i>FltCbdqDisable</i> can be running at IRQL &lt;= DISPATCH_LEVEL. If a mutex or resource is used, the caller must be running at IRQL &lt;= APC_LEVEL. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544624">FLT_CALLBACK_DATA_QUEUE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541799">FltCbdqEnable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541802">FltCbdqInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541815">FltCbdqInsertIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541821">FltCbdqRemoveIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541825">FltCbdqRemoveNextIo</a>
 

 

