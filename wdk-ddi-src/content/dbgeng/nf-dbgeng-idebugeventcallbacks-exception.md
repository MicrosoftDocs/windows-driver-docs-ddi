---
UID: NF:dbgeng.IDebugEventCallbacks.Exception
title: IDebugEventCallbacks::Exception (dbgeng.h)
description: The Exception callback method is called by the engine when an exceptiondebugging event occurs in the target.
old-location: debugger\idebugeventcallbacks_exception.htm
tech.root: debugger
ms.assetid: 93f915ab-1f9e-453c-b76e-8260eecd7298
ms.date: 05/03/2018
ms.keywords: ComCallbacks_46bf959d-52a9-4b0a-b074-d28b76de343d.xml, Exception, Exception method [Windows Debugging], Exception method [Windows Debugging],IDebugEventCallbacks interface, IDebugEventCallbacks interface [Windows Debugging],Exception method, IDebugEventCallbacks.Exception, IDebugEventCallbacks::Exception, dbgeng/IDebugEventCallbacks::Exception, debugger.idebugeventcallbacks_exception
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugEventCallbacks.Exception
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugEventCallbacks::Exception


## -description


The <b>Exception</b> callback method is called by the engine when an <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">exception</a>debugging event occurs in the target.


## -parameters




### -param Exception [in]

Specifies the nature of the exception.  EXCEPTION_RECORD64 is defined in winnt.h.


### -param FirstChance [in]

Specifies whether this exception has been previously encountered.  A nonzero value means that this is the first time the exception has been encountered ("first chance").  A zero value means that the exception has already been offered to all possible handlers, and each one declined to handle it ("second chance").


## -returns



This method returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.




## -remarks



This method is only called by the engine if the DEBUG_EVENT_EXCEPTION flag is set in the mask returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550737">IDebugEventCallbacks::GetInterestMask</a>.

Because the structure that <i>Exception</i> points to might be deleted after this method returns, implementations of <b>IDebugEventCallbacks</b> should not access this structure after returning.

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.



