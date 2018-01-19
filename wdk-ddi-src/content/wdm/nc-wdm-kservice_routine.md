---
UID: NC:wdm.KSERVICE_ROUTINE
title: KSERVICE_ROUTINE
author: windows-driver-content
description: The InterruptService routine (ISR) quickly services a device interrupt and schedules post-interrupt processing of received data, if necessary.
old-location: kernel\interruptservice.htm
old-project: kernel
ms.assetid: ad104d4d-5e7f-4730-b898-71ab467f9379
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: InterruptService
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at DIRQL (see Remarks section).
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# KSERVICE_ROUTINE callback



## -description
The <i>InterruptService</i> routine (ISR) quickly services a device interrupt and schedules post-interrupt processing of received data, if necessary.



## -prototype

````
KSERVICE_ROUTINE InterruptService;

BOOLEAN InterruptService(
  _In_ struct _KINTERRUPT *Interrupt,
  _In_ PVOID              ServiceContext
)
{ ... }
````


## -parameters

### -param Interrupt [in]

Caller-supplied pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554237">KINTERRUPT</a> structure for the interrupt.


### -param ServiceContext [in]

Caller-supplied pointer to context information, specified in a previous call to <a href="..\wdm\nf-wdm-ioconnectinterrupt.md">IoConnectInterrupt</a> or <a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a>.


## -returns
If the routine determines that the interrupt did not come from one of the driver's devices, it must return <b>FALSE</b>. Otherwise, the routine must service the interrupt and return <b>TRUE</b>.


## -remarks
To register an ISR for a specific interrupt vector and processor affinity, a driver must call <a href="..\wdm\nf-wdm-ioconnectinterrupt.md">IoConnectInterrupt</a> or <a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a>.

A driver's <i>InterruptService</i> routine (ISR) executes in an interrupt context, at some system-assigned <a href="wdkgloss.d#wdkgloss.device_interrupt_request_level__dirql_#wdkgloss.device_interrupt_request_level__dirql_"><i>DIRQL</i></a>, as specified by the <i>SynchronizeIrql</i> parameter to <b>IoConnectInterrupt</b>. (Other devices, with higher DIRQL values, can interrupt the ISR.)

Before the system calls an ISR, it acquires the interrupt's spin lock (the <i>SpinLock</i> parameter to <b>IoConnectInterrupt</b>), so the ISR cannot simultaneously execute on another processor. After the ISR returns, the system releases the spin lock.

An ISR must first determine if the interrupt came from one of the driver's devices, by examining context information supplied by <i>Context</i>. If the interrupt is not from one of the driver's devices, the routine must immediately return <b>FALSE</b> so the I/O manager can call other drivers that have registered ISRs for the same processor and interrupt vector.

For more information about implementing ISRs, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547974">Interrupt Service Routines</a>.

To define an <i>InterruptService</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>InterruptService</i> callback routine that is named <code>MyInterruptService</code>, use the KSERVICE_ROUTINE type as shown in this code example:

Then, implement your callback routine as follows:

The KSERVICE_ROUTINE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the KSERVICE_ROUTINE function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.</p>