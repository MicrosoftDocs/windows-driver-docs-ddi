---
UID: NN:portcls.IInterruptSync
title: IInterruptSync
author: windows-driver-content
description: The IInterruptSync interface represents an interrupt sync object that synchronizes the execution of a list of interrupt service routines (ISRs) with non-ISR routines.
old-location: audio\iinterruptsync.htm
old-project: audio
ms.assetid: fffdee8e-6298-45b9-94ee-23426598fbee
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcUnregisterIoTimeout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IInterruptSync
req.alt-loc: portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IInterruptSync interface



## -description
The <code>IInterruptSync</code> interface represents an interrupt sync object that synchronizes the execution of a list of interrupt service routines (ISRs) with non-ISR routines. The PortCls system driver implements this interface and exposes it to the adapter driver. A miniport driver obtains a reference to an <code>IInterruptSync</code> object by calling the PortCls function <a href="..\portcls\nf-portcls-pcnewinterruptsync.md">PcNewInterruptSync</a>, which creates a new <code>IInterruptSync</code> object that connects to an interrupt resource. <code>IInterruptSync</code> inherits from the <b>IUnknown</b> interface.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff536600">IInterruptSync::RegisterServiceRoutine</a> method associates an ISR with a sync object. More than one ISR can be associated with a single sync object. When the interrupt occurs, the sync object executes the ISRs in the list in a specified order and manner according to the <b>PcNewInterruptSync</b> function's <i>Mode</i> parameter.

Another facet of <code>IInterruptSync</code> is its ability to synchronize execution of ISRs with other routines that are not ISRs. Once a non-ISR routine is passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536592">IInterruptSync::CallSynchronizedRoutine</a> and begins running, execution of any ISRs that are registered with the sync object is guaranteed to be held off until that routine has finished running.

Both the <b>RegisterServiceRoutine</b> and <b>CallSynchronizedRoutine</b> methods accept function pointers of type PINTERRUPTSYNCROUTINE, which is defined as follows:



## -syntax

````
  typedef NTSTATUS (*PINTERRUPTSYNCROUTINE)
  (
      IN  struct IInterruptSync *InterruptSync,
      IN  PVOID                  DynamicContext
  );
````


## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IInterruptSync</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface but does not have additional members.


## -remarks
