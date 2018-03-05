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
product: Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_PRIORITY, *PWDF_INTERRUPT_PRIORITY
req.product: Windows 10 or later.
---

# WdfInterruptQueueWorkItemForIsr function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfInterruptQueueWorkItemForIsr</b> method queues a framework interrupt object's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_workitem.md">EvtInterruptWorkItem</a> callback function for execution.


## -syntax


````
BOOLEAN WdfInterruptQueueWorkItemForIsr(
  _In_ WDFINTERRUPT Interrupt
);
````


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


## -returns




      If the driver's ISR is running at IRQL = PASSIVE_LEVEL, <b>WdfInterruptQueueWorkItemForIsr</b> returns <b>TRUE</b> if it successfully queues the interrupt object's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_workitem.md">EvtInterruptWorkItem</a> callback function. The method returns <b>FALSE</b> if the callback function was previously queued and has not executed.


      If the driver's ISR is running at IRQL = DIRQL, the framework first queues an internal DPC and then queues a work item from that DPC. In this case, <b>WdfInterruptQueueWorkItemForIsr</b> returns <b>TRUE</b> if the framework successfully queues the internal DPC. The method returns <b>FALSE</b> if the internal DPC was previously queued.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Drivers typically call <b>WdfInterruptQueueWorkItemForIsr</b> from within an <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a> callback function.

An interrupt object's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_workitem.md">EvtInterruptWorkItem</a> callback function can be queued only once before it executes. Therefore, if a call to <b>WdfInterruptQueueWorkItemForIsr</b> succeeds, subsequent calls will not queue additional callbacks.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.

  A bug check occurs if drivers call <b>WdfInterruptQueueWorkItemForIsr</b> with an interrupt object that does not specify an <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_workitem.md">EvtInterruptWorkItem</a> callback function.






## -see-also

<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a>



<a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptqueuedpcforisr.md">WdfInterruptQueueDpcForIsr</a>



<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a>



<a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptcreate.md">WdfInterruptCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfInterruptQueueWorkItemForIsr method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

