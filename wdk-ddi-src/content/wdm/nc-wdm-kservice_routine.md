---
UID: NC:wdm.KSERVICE_ROUTINE
title: KSERVICE_ROUTINE (wdm.h)
description: The InterruptService routine (ISR) quickly services a device interrupt and schedules post-interrupt processing of received data, if necessary.
old-location: kernel\interruptservice.htm
tech.root: kernel
ms.assetid: ad104d4d-5e7f-4730-b898-71ab467f9379
ms.date: 04/30/2018
keywords: ["KSERVICE_ROUTINE callback function"]
ms.keywords: DrvrRtns_ee9bfb68-3d4c-4abf-9d2b-81037c2572d5.xml, InterruptService, InterruptService routine [Kernel-Mode Driver Architecture], KSERVICE_ROUTINE, kernel.interruptservice, wdm/InterruptService
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
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
req.irql: Called at DIRQL (see Remarks section).
targetos: Windows
req.typenames: 
f1_keywords:
 - KSERVICE_ROUTINE
 - wdm/KSERVICE_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - InterruptService
---

# KSERVICE_ROUTINE callback function


## -description

The <i>InterruptService</i> routine (ISR) quickly services a device interrupt and schedules post-interrupt processing of received data, if necessary.

## -parameters

### -param Interrupt 

[in]
Caller-supplied pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KINTERRUPT</a> structure for the interrupt.

### -param ServiceContext 

[in]
Caller-supplied pointer to context information, specified in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioconnectinterrupt">IoConnectInterrupt</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioconnectinterruptex">IoConnectInterruptEx</a>.

## -returns

If the routine determines that the interrupt did not come from one of the driver's devices, it must return <b>FALSE</b>. Otherwise, the routine must service the interrupt and return <b>TRUE</b>.

## -remarks

To register an ISR for a specific interrupt vector and processor affinity, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioconnectinterrupt">IoConnectInterrupt</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioconnectinterruptex">IoConnectInterruptEx</a>.

A driver's <i>InterruptService</i> routine (ISR) executes in an interrupt context, at some system-assigned <a href="https://docs.microsoft.com/windows-hardware/drivers/">DIRQL</a>, as specified by the <i>SynchronizeIrql</i> parameter to <b>IoConnectInterrupt</b>. (Other devices, with higher DIRQL values, can interrupt the ISR.)

Before the system calls an ISR, it acquires the interrupt's spin lock (the <i>SpinLock</i> parameter to <b>IoConnectInterrupt</b>), so the ISR cannot simultaneously execute on another processor. After the ISR returns, the system releases the spin lock.

An ISR must first determine if the interrupt came from one of the driver's devices, by examining context information supplied by <i>Context</i>. If the interrupt is not from one of the driver's devices, the routine must immediately return <b>FALSE</b> so the I/O manager can call other drivers that have registered ISRs for the same processor and interrupt vector.

For more information about implementing ISRs, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/interrupt-service-routines">Interrupt Service Routines</a>.


#### Examples

To define an <i>InterruptService</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>InterruptService</i> callback routine that is named <code>MyInterruptService</code>, use the KSERVICE_ROUTINE type as shown in this code example:


```
KSERVICE_ROUTINE MyInterruptService;
```

Then, implement your callback routine as follows:


```
_Use_decl_annotations_
BOOLEAN
  MyInterruptService(
    struct _KINTERRUPT  *Interrupt,
    PVOID  ServiceContext
    )
  {
      // Function body
  }
```

The KSERVICE_ROUTINE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the KSERVICE_ROUTINE function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>

