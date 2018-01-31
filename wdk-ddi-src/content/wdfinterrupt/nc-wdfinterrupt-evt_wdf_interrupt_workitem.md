---
UID: NC:wdfinterrupt.EVT_WDF_INTERRUPT_WORKITEM
title: EVT_WDF_INTERRUPT_WORKITEM
author: windows-driver-content
description: A driver's EvtInterruptWorkItem event callback function processes interrupt information that the driver's EvtInterruptIsr callback function has stored.
old-location: wdf\evtinterruptworkitem.htm
old-project: wdf
ms.assetid: 1A473A08-EA23-4DFE-8B58-EBB4AC977891
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtinterruptworkitem, EvtInterruptWorkItem callback function, EvtInterruptWorkItem, EVT_WDF_INTERRUPT_WORKITEM, EVT_WDF_INTERRUPT_WORKITEM, wdfinterrupt/EvtInterruptWorkItem, kmdf.evtinterruptworkitem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdfinterrupt.h
apiname:
-	EvtInterruptWorkItem
product: Windows
targetos: Windows
req.typenames: "*PWDF_COINSTALLER_INSTALL_OPTIONS, WDF_COINSTALLER_INSTALL_OPTIONS"
req.product: Windows 10 or later.
---

# EVT_WDF_INTERRUPT_WORKITEM callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtInterruptWorkItem</i> event callback function processes interrupt information that the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a> callback function has stored.


## -prototype


````
EVT_WDF_INTERRUPT_WORKITEM EvtInterruptWorkItem;

VOID EvtInterruptWorkItem(
  _In_ WDFINTERRUPT Interrupt,
  _In_ WDFOBJECT    AssociatedObject
)
{ ... }
````


## -parameters




#### - Interrupt [in]

A handle to a framework interrupt object.


#### - AssociatedObject [in]

A handle to the framework device object that the driver passed to <a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptcreate.md">WdfInterruptCreate</a>.


## -returns


None



## -remarks


The <i>EvtInterruptWorkItem</i> callback function runs at IRQL = PASSIVE_LEVEL.

To register an <i>EvtInterruptWorkItem</i> callback function, your driver must place the callback function's address in a <a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a> structure before calling <a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptcreate.md">WdfInterruptCreate</a>.

Most drivers use a single <i>EvtInterruptWorkItem</i> callback function for each type of interrupt. 


To schedule execution of an <i>EvtInterruptWorkItem</i> callback function, the driver must call <a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptqueueworkitemforisr.md">WdfInterruptQueueWorkItemForIsr</a> from within the <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a> callback function.

If your driver creates multiple framework interrupt objects for each device, you might consider using a separate <i>EvtInterruptWorkItem</i> callback for each interrupt.


Drivers that implement either DIRQL  interrupt handling or passive level interrupt handling can queue an <i>EvtInterruptWorkItem</i> callback.

 A driver cannot queue both an <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a> and a <i>EvtInterruptWorkItem</i> callback.

If the driver has set the <b>AutomaticSerialization</b> member to TRUE in the interrupt's <a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a> structure, the framework  synchronizes execution of the interrupt object's <i>EvtInterruptWorkItem</i> callback function with callback functions from other objects that are underneath the interrupt's parent object.  For information about callback synchronization locks, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-framework-locks">Using Framework Locks</a>.

 In general, if the driver needs to acquire the interrupt object's passive lock from within <i>EvtInterruptWorkItem</i>, the driver should set the <b>AutomaticSerialization</b> member of <a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a> to FALSE and then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a> from within <i>EvtInterruptWorkItem</i>.

If  <b>AutomaticSerialization</b> is set to TRUE, a driver's <i>EvtInterruptWorkItem</i>  callback function should not call any of the following methods:
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a><a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptsynchronize.md">WdfInterruptSynchronize</a><a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptdisable.md">WdfInterruptDisable</a><a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptenable.md">WdfInterruptEnable</a>For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.


