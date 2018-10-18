---
UID: NF:dbgeng.IDebugEventCallbacks.ExitThread
title: IDebugEventCallbacks::ExitThread
author: windows-driver-content
description: The ExitThread callback method is called by the engine when an exit-threaddebugging event occurs in the target.
old-location: debugger\idebugeventcallbacks_exitthread.htm
tech.root: debugger
ms.assetid: 03ff46cb-dfc5-409a-b652-bef8f2b37b59
ms.date: 05/03/2018
ms.keywords: ComCallbacks_554f76a8-5f15-4bcc-b3ec-070ecc836ba9.xml, ExitThread, ExitThread method [Windows Debugging], ExitThread method [Windows Debugging],IDebugEventCallbacks interface, IDebugEventCallbacks interface [Windows Debugging],ExitThread method, IDebugEventCallbacks.ExitThread, IDebugEventCallbacks::ExitThread, dbgeng/IDebugEventCallbacks::ExitThread, debugger.idebugeventcallbacks_exitthread
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
-	IDebugEventCallbacks.ExitThread
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugEventCallbacks::ExitThread


## -description


The <b>ExitThread</b> callback method is called by the engine when an exit-threaddebugging event occurs in the target.


## -parameters




### -param ExitCode [in]

Specifies the exit code for the thread.


## -returns



This method returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.




## -remarks



This method is only called by the engine if the DEBUG_EVENT_EXIT_THREAD flag is set in the mask returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550737">IDebugEventCallbacks::GetInterestMask</a>.

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.  For information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.



