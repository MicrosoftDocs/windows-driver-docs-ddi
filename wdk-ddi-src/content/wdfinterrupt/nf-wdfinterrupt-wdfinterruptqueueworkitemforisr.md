---
UID: NF:wdfinterrupt.WdfInterruptQueueWorkItemForIsr
title: WdfInterruptQueueWorkItemForIsr function
author: windows-driver-content
description: The WdfInterruptQueueWorkItemForIsr method queues a framework interrupt object's EvtInterruptWorkItem callback function for execution.
old-location: wdf\wdfinterruptqueueworkitemforisr.htm
old-project: wdf
ms.assetid: 1E88E9D9-B564-43B4-9A83-F621FF23437F
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfInterruptQueueWorkItemForIsr, WdfInterruptQueueWorkItemForIsr method, kmdf.wdfinterruptqueueworkitemforisr, wdf.wdfinterruptqueueworkitemforisr, wdfinterrupt/WdfInterruptQueueWorkItemForIsr
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DIRQL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfInterruptQueueWorkItemForIsr
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfInterruptQueueWorkItemForIsr function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfInterruptQueueWorkItemForIsr</b> method queues a framework interrupt object's <a href="https://msdn.microsoft.com/1A473A08-EA23-4DFE-8B58-EBB4AC977891">EvtInterruptWorkItem</a> callback function for execution.


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


## -returns




      If the driver's ISR is running at IRQL = PASSIVE_LEVEL, <b>WdfInterruptQueueWorkItemForIsr</b> returns <b>TRUE</b> if it successfully queues the interrupt object's <a href="https://msdn.microsoft.com/1A473A08-EA23-4DFE-8B58-EBB4AC977891">EvtInterruptWorkItem</a> callback function. The method returns <b>FALSE</b> if the callback function was previously queued and has not executed.


      If the driver's ISR is running at IRQL = DIRQL, the framework first queues an internal DPC and then queues a work item from that DPC. In this case, <b>WdfInterruptQueueWorkItemForIsr</b> returns <b>TRUE</b> if the framework successfully queues the internal DPC. The method returns <b>FALSE</b> if the internal DPC was previously queued.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Drivers typically call <b>WdfInterruptQueueWorkItemForIsr</b> from within an <a href="https://msdn.microsoft.com/6f28a66a-9c17-4020-bfe2-295c22af6ba7">EvtInterruptIsr</a> callback function.

An interrupt object's <a href="https://msdn.microsoft.com/1A473A08-EA23-4DFE-8B58-EBB4AC977891">EvtInterruptWorkItem</a> callback function can be queued only once before it executes. Therefore, if a call to <b>WdfInterruptQueueWorkItemForIsr</b> succeeds, subsequent calls will not queue additional callbacks.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.

  A bug check occurs if drivers call <b>WdfInterruptQueueWorkItemForIsr</b> with an interrupt object that does not specify an <a href="https://msdn.microsoft.com/1A473A08-EA23-4DFE-8B58-EBB4AC977891">EvtInterruptWorkItem</a> callback function.






## -see-also




<a href="https://msdn.microsoft.com/d2d505e0-aeac-4871-8c60-d026b2833043">EvtInterruptDpc</a>



<a href="https://msdn.microsoft.com/6f28a66a-9c17-4020-bfe2-295c22af6ba7">EvtInterruptIsr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547345">WdfInterruptCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547371">WdfInterruptQueueDpcForIsr</a>
 

 

