---
UID: NF:fltkernel.FltCbdqEnable
title: FltCbdqEnable function
author: windows-driver-content
description: FltCbdqEnable enables a callback data queue that was disabled by a previous call to FltCbdqDisable.
old-location: ifsk\fltcbdqenable.htm
old-project: ifsk
ms.assetid: cc9167cc-366e-4824-9968-1e2895a61a0c
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_a_to_d_518b7b11-d2cd-4d69-9191-da63831da3bd.xml, FltCbdqEnable, FltCbdqEnable function [Installable File System Drivers], fltkernel/FltCbdqEnable, ifsk.fltcbdqenable
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fltkernel.h
api_name:
-	FltCbdqEnable
product: Windows
targetos: Windows
req.typenames: 
---

# FltCbdqEnable function


## -description


<i>FltCbdqEnable</i> enables a callback data queue that was disabled by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541796">FltCbdqDisable</a>. 


## -parameters




### -param Cbdq [in, out]

Pointer to the callback data queue. 


## -returns



None 




## -remarks



<i>FltCbdqEnable</i> reenables a callback data queue that was disabled by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541796">FltCbdqDisable</a>. After the callback data queue is reenabled, it can once again accept new items. 

Minifilter drivers can use the <b>FltCbdq</b><i>Xxx</i> routines to implement a callback data queue for IRP-based I/O operations. By using these routines, minifilter drivers can make their queue cancel-safe; the system transparently handles I/O cancellation for the minifilter driver. 

The <b>FltCbdq</b><i>Xxx</i> routines can only be used for IRP-based I/O operations. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. 

If the queue is protected by a <a href="https://msdn.microsoft.com/0585fc2a-0d0b-434d-92b3-da07a9385444">spin lock</a> rather than a <a href="https://msdn.microsoft.com/e2142b6d-f460-4f80-be0f-e00b5d43731c">mutex object</a> or <a href="https://msdn.microsoft.com/be18a6e6-863d-4a0c-9bcd-a36ace0b54fe">resource variable</a>, the caller of <i>FltCbdqEnable</i> can be running at IRQL &lt;= DISPATCH_LEVEL. If a mutex or resource is used, the caller must be running at IRQL &lt;= APC_LEVEL. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544624">FLT_CALLBACK_DATA_QUEUE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541796">FltCbdqDisable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541802">FltCbdqInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541815">FltCbdqInsertIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541821">FltCbdqRemoveIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541825">FltCbdqRemoveNextIo</a>
 

 

