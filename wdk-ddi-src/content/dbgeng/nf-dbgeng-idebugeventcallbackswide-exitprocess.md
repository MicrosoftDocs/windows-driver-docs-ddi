---
UID: NF:dbgeng.IDebugEventCallbacksWide.ExitProcess
title: IDebugEventCallbacksWide::ExitProcess
author: windows-driver-content
description: The ExitProcess callback method is called by the engine when an exit-processdebugging event occurs in the target.
old-location: debugger\idebugeventcallbackswide_exitprocess.htm
old-project: debugger
ms.assetid: bc104b84-4f0a-420d-8c2c-14b33cc6ca04
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: ExitProcess, ExitProcess method [Windows Debugging], ExitProcess method [Windows Debugging],IDebugEventCallbacksWide interface, IDebugEventCallbacksWide interface [Windows Debugging],ExitProcess method, IDebugEventCallbacksWide.ExitProcess, IDebugEventCallbacksWide::ExitProcess, dbgeng/IDebugEventCallbacksWide::ExitProcess, debugger.idebugeventcallbackswide_exitprocess
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	IDebugEventCallbacksWide.ExitProcess
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugEventCallbacksWide::ExitProcess


## -description


The <b>ExitProcess</b> callback method is called by the engine when an exit-processdebugging event occurs in the target.


## -parameters




### -param ExitCode [in]

Specifies the exit code for the process. 


## -returns



This method returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.




## -remarks



This method is only called by the engine if the DEBUG_EVENT_EXIT_PROCESS flag is set in the mask returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550625">IDebugEventCallbacksWide::GetInterestMask</a>.

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.  For information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.



