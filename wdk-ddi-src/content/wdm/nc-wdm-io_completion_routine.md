---
UID: NC:wdm.IO_COMPLETION_ROUTINE
title: IO_COMPLETION_ROUTINE
author: windows-driver-content
description: The IoCompletion routine completes the processing of I/O operations.
old-location: kernel\iocompletion.htm
old-project: kernel
ms.assetid: 53fc5265-5d8e-4794-942b-de81b93e81da
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.iocompletion, IoCompletion routine [Kernel-Mode Driver Architecture], IoCompletion, IO_COMPLETION_ROUTINE, IO_COMPLETION_ROUTINE, wdm/IoCompletion, DrvrRtns_aa2b6363-e3c1-4243-87d8-8a1bb575974b.xml
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at IRQL <= DISPATCH_LEVEL (see Remarks section).
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	Wdm.h
apiname: 
-	IoCompletion
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# IO_COMPLETION_ROUTINE callback


## -description


The <i>IoCompletion</i> routine completes the processing of I/O operations.


## -prototype


````
IO_COMPLETION_ROUTINE IoCompletion;

NTSTATUS IoCompletion(
  _In_     PDEVICE_OBJECT DeviceObject,
  _In_     PIRP           Irp,
  _In_opt_ PVOID          Context
)
{ ... }
````


## -parameters




### -param DeviceObject [in]

Caller-supplied pointer to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure. This is the device object for the target device, previously created by the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine.


### -param Irp [in]

Caller-supplied pointer to an <a href="..\wdm\ns-wdm-_irp.md">IRP</a> structure that describes the I/O operation.


### -param Context [in, optional]

Caller-supplied pointer to driver-specific context information, previously supplied when calling <a href="..\wdm\nf-wdm-iosetcompletionroutine.md">IoSetCompletionRoutine</a> or <a href="..\wdm\nf-wdm-iosetcompletionroutineex.md">IoSetCompletionRoutineEx</a>. Context information must be stored in nonpaged memory, since an <i>IoCompletion</i> routine can be called at DISPATCH_LEVEL. For more information, see the following Remarks section.


## -returns


If the <i>IoCompletion</i> routine determines that additional processing is required for the IRP, it must return STATUS_MORE_PROCESSING_REQUIRED. For more information, see the following Remarks section. Otherwise, it should return STATUS_SUCCESS. (The I/O manager only checks for the presence or absence of STATUS_MORE_PROCESSING_REQUIRED.)



## -remarks


A driver's <i>IoCompletion</i> routine executes in an arbitrary thread or DPC context, and at an IRQL that is less than or equal to DISPATCH_LEVEL. Because code written to execute at DISPATCH_LEVEL will also execute at lower levels, <i>IoCompletion</i> routines should be designed for execution at DISPATCH_LEVEL. However, because these routines are not guaranteed to run at DISPATCH_LEVEL, they must not call system routines that actually require execution at DISPATCH_LEVEL. (For more information about IRQLs, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554368">Managing Hardware Priorities</a>.)

To register an <i>IoCompletion</i> routine for a specific IRP, a driver must call <a href="..\wdm\nf-wdm-iosetcompletionroutine.md">IoSetCompletionRoutine</a> or <a href="..\wdm\nf-wdm-iosetcompletionroutineex.md">IoSetCompletionRoutineEx</a>, which stores the <i>IoCompletion</i> routine's address in the next-lower driver's I/O stack location. (Thus, a lowest-level driver <u>cannot</u> register an <i>IoCompletion</i> routine.) A driver typically calls <b>IoSetCompletionRoutine</b> or <b>IoSetCompletionRoutineEx</b> from one of its dispatch routines, each time an IRP is received. Most drivers, including all PnP drivers, can use<b> IoSetCompletionRoutine</b> to register their <i>IoCompletion</i> routine. Non-PnP drivers that may be unloaded before their <i>IoCompletion</i> routine executes should use <b>IoSetCompletionRoutineEx</b> instead.

When any driver completes an IRP, it calls <a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>, which in turn calls the <i>IoCompletion</i> routine of each higher-level driver, from the next-highest to the highest, until all higher <i>IoCompletion</i> routines have been called or until one routine returns STATUS_MORE_PROCESSING_REQUIRED.

When you create the IRP, allocate a stack location for the current driver as well as any lower drivers. If you do not allocate sufficient stack locations, the <i>DeviceObject</i> pointer might be set to <b>NULL</b> when the completion routine is called. You can avoid allocating extra stack location for the current driver if you use the <i>Context</i> field to pass information to <i>IoCompletion</i> rather then relying on the <i>DeviceObject</i> parameter.

If an <i>IoCompletion</i> routine returns STATUS_MORE_PROCESSING_REQUIRED, the lower driver's call to <b>IoCompleteRequest</b> immediately returns. In this case, a higher-level driver will have to call <b>IoCompleteRequest</b> to complete the IRP.

For more information about implementing <i>IoCompletion</i> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542018">Completing IRPs</a>.


