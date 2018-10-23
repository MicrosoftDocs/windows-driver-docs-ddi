---
UID: NF:dbgeng.IDebugEventCallbacks.ExitProcess
title: IDebugEventCallbacks::ExitProcess
author: windows-driver-content
description: The ExitProcess callback method is called by the engine when an exit-processdebugging event occurs in the target.
old-location: debugger\idebugeventcallbacks_exitprocess.htm
tech.root: debugger
ms.assetid: 050b747e-5570-4e25-81e4-eccdde4f6995
ms.date: 05/03/2018
ms.keywords: ComCallbacks_bcacc47e-294c-4dfa-a38e-2b57f534d415.xml, ExitProcess, ExitProcess method [Windows Debugging], ExitProcess method [Windows Debugging],IDebugEventCallbacks interface, IDebugEventCallbacks interface [Windows Debugging],ExitProcess method, IDebugEventCallbacks.ExitProcess, IDebugEventCallbacks::ExitProcess, dbgeng/IDebugEventCallbacks::ExitProcess, debugger.idebugeventcallbacks_exitprocess
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugEventCallbacks.ExitProcess
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugEventCallbacks::ExitProcess


## -description


The <b>ExitProcess</b> callback method is called by the engine when an exit-processdebugging event occurs in the target.


## -parameters




### -param ExitCode [in]

Specifies the exit code for the process. 


## -returns



This method returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.




## -remarks



This method is only called by the engine if the DEBUG_EVENT_EXIT_PROCESS flag is set in the mask returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550737">IDebugEventCallbacks::GetInterestMask</a>.

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.  For information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.



