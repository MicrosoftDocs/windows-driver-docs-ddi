---
UID: NF:portcls.IInterruptSync.CallSynchronizedRoutine
title: IInterruptSync::CallSynchronizedRoutine (portcls.h)
description: The CallSynchronizedRoutine method calls a routine that is not an interrupt service routine (ISR) but whose execution needs to be synchronized with ISRs.
old-location: audio\iinterruptsync_callsynchronizedroutine.htm
tech.root: audio
ms.assetid: 9895ee9a-4d8c-4cd4-8df4-fedaf864a178
ms.date: 05/08/2018
ms.keywords: CallSynchronizedRoutine, CallSynchronizedRoutine method [Audio Devices], CallSynchronizedRoutine method [Audio Devices],IInterruptSync interface, IInterruptSync interface [Audio Devices],CallSynchronizedRoutine method, IInterruptSync.CallSynchronizedRoutine, IInterruptSync::CallSynchronizedRoutine, audio.iinterruptsync_callsynchronizedroutine, audmp-routines_985e70ee-3e6b-4514-adb5-1b37f92c9ae4.xml, portcls/IInterruptSync::CallSynchronizedRoutine
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
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
- COM
api_location:
- portcls.h
api_name:
- IInterruptSync.CallSynchronizedRoutine
product:
- Windows
targetos: Windows
req.typenames: 
---

# IInterruptSync::CallSynchronizedRoutine


## -description


The <code>CallSynchronizedRoutine</code> method calls a routine that is not an interrupt service routine (ISR) but whose execution needs to be synchronized with ISRs.


## -parameters




### -param Routine [in]

Pointer to the routine that is to be called. This routine will run exclusive of the object's ISR and all other routines that are synchronized through the object. Even on multiple-processor machines, routines that are synchronized by a given object will not run concurrently. This parameter is a function pointer of type PINTERRUPTSYNCROUTINE (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536590">IInterruptSync</a>).


### -param DynamicContext [in]

A context value to be passed to the routine.


## -returns



<code>CallSynchronizedRoutine</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



Execution of any registered ISR is guaranteed to be held off until the call to the routine that is passed to <code>CallSynchronizedRoutine</code> has completed.

Callers of <code>CallSynchronizedRoutine</code> must be running at an IRQL that is less than or equal to the level of the interrupt that is associated with the synchronization object. This interrupt was specified by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537713">PcNewInterruptSync</a> function's <i>ResourceList</i> and <i>ResourceIndex</i> parameters.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536590">IInterruptSync</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553302">KeSynchronizeExecution</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537713">PcNewInterruptSync</a>
 

 

