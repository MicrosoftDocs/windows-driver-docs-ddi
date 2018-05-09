---
UID: NF:wdm.KeSynchronizeExecution
title: KeSynchronizeExecution function
author: windows-driver-content
description: The KeSynchronizeExecution routine synchronizes the execution of the specified routine with the interrupt service routine (ISR) that is assigned to a set of one or more interrupt objects.
old-location: kernel\kesynchronizeexecution.htm
old-project: kernel
ms.assetid: f378a30f-7e6b-4c81-b98b-a5b40e9a1a17
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: KeSynchronizeExecution, KeSynchronizeExecution routine [Kernel-Mode Driver Architecture], k105_2abf2438-6849-4069-8571-7d24d348056f.xml, kernel.kesynchronizeexecution, wdm/KeSynchronizeExecution
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DIRQL (see Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeSynchronizeExecution
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeSynchronizeExecution function


## -description


The <b>KeSynchronizeExecution</b> routine synchronizes the execution of the specified routine with the interrupt service routine (ISR) that is assigned to a set of one or more interrupt objects.


## -parameters




### -param Interrupt [in, out]

A pointer to a set of interrupt objects. The caller obtained this pointer from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548371">IoConnectInterrupt</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548378">IoConnectInterruptEx</a> routine.


### -param SynchronizeRoutine [in]

Specifies a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff563928">SynchCritSection</a> routine whose execution is to be synchronized with the execution of the ISR assigned to the interrupt objects.


### -param SynchronizeContext [in, optional]

A pointer to a caller-supplied context value to be passed to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563928">SynchCritSection</a> routine when it is called.


## -returns



<b>KeSynchronizeExecution</b> returns <b>TRUE</b> if the operation succeeds. Otherwise, it returns <b>FALSE</b>.




## -remarks



When this routine is called, the following occurs:

<ol>
<li>
The IRQL is raised to the <i>SynchronizeIrql</i> value specified in the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548371">IoConnectInterrupt</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548378">IoConnectInterruptEx</a>.

</li>
<li>
Access to <i>SynchronizeContext</i> is synchronized with the assigned ISR by acquiring the associated interrupt object spin lock (or system event object, in the case of an ISR that runs at PASSIVE_LEVEL).

</li>
<li>
The specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff563928">SynchCritSection</a> routine is called with the <i>SynchronizeContext</i> value as its parameter.

</li>
</ol>
If the ISR runs at DIRQL &gt;= DISPATCH_LEVEL, the <i>SynchCritSection</i> routine runs at the same DIRQL and must therefore run for as brief a time as possible to avoid delaying other high-priority tasks.

Callers of <b>KeSynchronizeExecution</b> must be running at IRQL &lt;= DIRQL; that is, at an IRQL that is less than or equal to the value of the <b>SynchronizeIrql</b> value that the caller specified when it registered its ISR with <b>IoConnectInterrupt</b> or <b>IoConnectInterruptEx</b>.

Starting with Windows 8, a driver can call <b>KeSynchronizeExecution</b> to synchronize execution of a <i>SynchCritSection</i> routine with an ISR that runs at IRQL = PASSIVE_LEVEL. In earlier versions of Windows, <b>KeSynchronizeExecution</b> can synchronize execution only with an ISR that runs at IRQL &gt;= DISPATCH_LEVEL. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh698277">Using Passive-Level Interrupt Service Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548371">IoConnectInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548378">IoConnectInterruptEx</a>
 

 

