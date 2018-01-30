---
UID: NC:wdfinterrupt.EVT_WDF_INTERRUPT_SYNCHRONIZE
title: EVT_WDF_INTERRUPT_SYNCHRONIZE
author: windows-driver-content
description: A driver's EvtInterruptSynchronize event callback function performs operations that must be synchronized with an EvtInterruptIsr callback function.
old-location: wdf\evtinterruptsynchronize.htm
old-project: wdf
ms.assetid: ac73b23d-7742-43a4-8950-b301bd0ba330
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtinterruptsynchronize, EvtInterruptSynchronize callback function, EvtInterruptSynchronize, EVT_WDF_INTERRUPT_SYNCHRONIZE, EVT_WDF_INTERRUPT_SYNCHRONIZE, wdfinterrupt/EvtInterruptSynchronize, DFInterruptObjectRef_4310d770-645e-48c8-bd33-b9edcc8cb667.xml, kmdf.evtinterruptsynchronize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: "(See Remarks section.)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdfinterrupt.h
apiname:
-	EvtInterruptSynchronize
product: Windows
targetos: Windows
req.typenames: WDF_COINSTALLER_INSTALL_OPTIONS, *PWDF_COINSTALLER_INSTALL_OPTIONS
req.product: Windows 10 or later.
---

# EVT_WDF_INTERRUPT_SYNCHRONIZE callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtInterruptSynchronize</i> event callback function performs operations that must be synchronized with an <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a> callback function.


## -prototype


````
EVT_WDF_INTERRUPT_SYNCHRONIZE EvtInterruptSynchronize;

BOOLEAN EvtInterruptSynchronize(
  _In_ WDFINTERRUPT Interrupt,
  _In_ WDFCONTEXT   Context
)
{ ... }
````


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


### -param Context [in]

Driver-supplied information that the driver specifies when it calls <a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptsynchronize.md">WdfInterruptSynchronize</a>.


## -returns


The <i>EvtInterruptSynchronize</i> callback function must return <b>TRUE</b> if the operation succeeds. Otherwise, this function must return <b>FALSE</b>. 



## -remarks


To execute an <i>EvtInterruptSynchronize</i> callback function, the driver must call <a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptsynchronize.md">WdfInterruptSynchronize</a>. 

If the driver has configured the interrupt object for handling at the device's IRQL (DIRQL), then before calling the <i>EvtInterruptSynchronize</i> callback function, the framework raises the processor's interrupt request level to DIRQL and acquires the spin lock that the driver specified in the interrupt object's <a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a> structure. 

As a result, while an <i>EvtInterruptSynchronize</i> callback function is executing, the interrupt object's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a> callback function (and any other code that executes at DIRQL while holding the spin lock) cannot execute. 

<i>EvtInterruptSynchronize</i> callback functions must be designed so that they execute for only a short period of time. They are typically used to access interrupt data that is also accessed by an interrupt object's other <i>EvtInterruptSynchronize</i> or <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a> callback functions. 

Beginning with version 1.11 of KMDF, your driver can provide <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupt handling</a>. If the driver has requested passive-level interrupt handling, then before calling the <i>EvtInterruptSynchronize</i> function at IRQL = PASSIVE_LEVEL, the framework acquires the passive-level interrupt lock that the driver configured in the interrupt object's <a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a> structure.

For more information about the <i>EvtInterruptSynchronize</i> callback function, see <a href="https://msdn.microsoft.com/a24477dc-f75d-4ab6-8695-d8a85247e276">Synchronizing Interrupt Code</a>.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.



## -see-also

<a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a>

<a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptsynchronize.md">WdfInterruptSynchronize</a>

<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_INTERRUPT_SYNCHRONIZE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

