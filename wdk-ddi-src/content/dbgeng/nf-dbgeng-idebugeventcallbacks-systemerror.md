---
UID: NF:dbgeng.IDebugEventCallbacks.SystemError
title: IDebugEventCallbacks::SystemError
author: windows-driver-content
description: The SystemError callback method is called by the engine when a system error occurs in the target.
old-location: debugger\idebugeventcallbacks_systemerror.htm
old-project: debugger
ms.assetid: 651f5207-36c8-4d46-8305-950efb2365bf
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: ComCallbacks_a84628b9-4376-4ca0-883f-835d19e13d73.xml, IDebugEventCallbacks interface [Windows Debugging],SystemError method, IDebugEventCallbacks.SystemError, IDebugEventCallbacks::SystemError, SystemError, SystemError method [Windows Debugging], SystemError method [Windows Debugging],IDebugEventCallbacks interface, dbgeng/IDebugEventCallbacks::SystemError, debugger.idebugeventcallbacks_systemerror
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
-	IDebugEventCallbacks.SystemError
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugEventCallbacks::SystemError


## -description


The <b>SystemError</b> callback method is called by the engine when a system error occurs in the target.


## -parameters




### -param Error [in]

Specifies the error that caused the event.


### -param Level [in]

Specifies the severity of the error.


## -returns



This method returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.




## -remarks



This method is only called by the engine if the DEBUG_EVENT_SYSTEM_ERROR flag is set in the mask returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550737">IDebugEventCallbacks::GetInterestMask</a>.

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.



