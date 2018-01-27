---
UID: NC:wdfinterrupt.EVT_WDF_INTERRUPT_ISR
title: EVT_WDF_INTERRUPT_ISR
author: windows-driver-content
description: A driver's EvtInterruptIsr event callback function services a hardware interrupt.
old-location: wdf\evtinterruptisr.htm
old-project: wdf
ms.assetid: 6f28a66a-9c17-4020-bfe2-295c22af6ba7
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtinterruptisr, EvtInterruptIsr callback function, EvtInterruptIsr, EVT_WDF_INTERRUPT_ISR, EVT_WDF_INTERRUPT_ISR, wdfinterrupt/EvtInterruptIsr, DFInterruptObjectRef_0a8902c4-d292-418f-bab3-d7fc36d69fd5.xml, kmdf.evtinterruptisr
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
req.irql: (See Remarks section.)
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	Wdfinterrupt.h
apiname: 
-	EvtInterruptIsr
product: Windows
targetos: Windows
req.typenames: *PWDF_COINSTALLER_INSTALL_OPTIONS, WDF_COINSTALLER_INSTALL_OPTIONS
req.product: Windows 10 or later.
---

# EVT_WDF_INTERRUPT_ISR callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtInterruptIsr</i> event callback function services a hardware interrupt.


## -prototype


````
EVT_WDF_INTERRUPT_ISR EvtInterruptIsr;

BOOLEAN EvtInterruptIsr(
  _In_ WDFINTERRUPT Interrupt,
  _In_ ULONG        MessageID
)
{ ... }
````


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


### -param MessageID [in]

If the device is using message-signaled interrupts (MSIs), this parameter is the message number that identifies the device's hardware interrupt message. Otherwise, this value is 0.


## -returns


The <i>EvtInterruptIsr</i> callback function must return <b>TRUE</b> if the function services the hardware interrupt. Otherwise, this function must return <b>FALSE</b>.



## -remarks


To register an <i>EvtInterruptIsr</i> callback function, your driver must place the callback function's address in a <a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a> structure before calling <a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptcreate.md">WdfInterruptCreate</a>.

The <i>EvtInterruptIsr</i> callback function is a framework-based driver's interrupt service routine (ISR), which is called when a hardware interrupt occurs.

If the interrupt is not from the hardware that this <i>EvtInterruptIsr</i> callback function services, the driver must return <b>FALSE</b>. If the interrupt vector is being shared, the system calls another interrupt service routine.

If the driver has not requested passive-level handling for an interrupt object, then before calling the <i>EvtInterruptIsr</i> callback function, the framework  raises the processor's IRQL to the device's IRQL (DIRQL) and acquires the spin lock that the driver specified in the interrupt object's <a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a> structure. 

Because the <i>EvtInterruptIsr</i> callback function executes at a relatively high IRQL, it can call very few framework object methods or system routines. Additionally, this callback function cannot access <a href="https://msdn.microsoft.com/0b3c1e00-2416-4534-9934-bb05f91c7482">pageable</a> code. 

Typically, the <i>EvtInterruptIsr</i> callback function clears the hardware interrupt and saves any information that might be lost after the callback function returns and the system lowers the IRQL (because lowering the IRQL allows additional interrupts to occur). Framework-based drivers save information about the interrupt in the interrupt object's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-context-space">context space</a>. 

Drivers typically provide an <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a> callback function  to process the saved information at a lower IRQL. (A few drivers provide one or more <a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a> callback functions instead of an <i>EvtInterruptDpc</i> callback function.) For information about scheduling an <i>EvtInterruptDpc</i> callback function for execution, see <a href="https://msdn.microsoft.com/b6306d2c-a7be-4fc3-8123-4d2b5c60c988">Servicing an Interrupt</a>.

The <i>EvtInterruptIsr</i> callback function must be able to service several interrupts before the <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a> callback function executes. Therefore, the driver might have to store interrupt data from several interrupts, and the <i>EvtInterruptIsr</i> and<i>EvtInterruptDpc</i> callback functions might have to determine which interrupt data has been completely processed by the driver and which has not. 

Beginning with version 1.11 of KMDF, your driver can provide <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupt handling</a>. If the driver has requested passive-level handling for an interrupt object, then before calling that interrupt's <i>EvtInterruptIsr</i> callback function at IRQL = PASSIVE_LEVEL, the framework acquires the passive-level interrupt lock that the driver configured in the interrupt object's <a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a> structure. As with interrupt handling at DIRQL, the driver's <i>EvtInterruptIsr</i> function should still save information about the interrupt for later processing.

Drivers that support passive-level interrupt handling can provide either an <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_workitem.md">EvtInterruptWorkItem</a> or an <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a> callback function to process the saved information.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.



## -see-also

<a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptcreate.md">WdfInterruptCreate</a>

<a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a>

<a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a>

<a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptgetdevice.md">WdfInterruptGetDevice</a>

<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a>

<a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptwdmgetinterrupt.md">WdfInterruptWdmGetInterrupt</a>

<a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptgetinfo.md">WdfInterruptGetInfo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_INTERRUPT_ISR callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

