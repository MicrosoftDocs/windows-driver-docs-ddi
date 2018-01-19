---
UID: NF:dbgeng.IDebugEventCallbacks.Exception
title: IDebugEventCallbacks::Exception method
author: windows-driver-content
description: The Exception callback method is called by the engine when an exceptiondebugging event occurs in the target.
old-location: debugger\idebugeventcallbacks_exception.htm
old-project: debugger
ms.assetid: 93f915ab-1f9e-453c-b76e-8260eecd7298
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugEventCallbacks, IDebugEventCallbacks::Exception, Exception
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
req.alt-api: IDebugEventCallbacks.Exception
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugEventCallbacks::Exception method



## -description
The <b>Exception</b> callback method is called by the engine when an <a href="wdkgloss.e#wdkgloss.exception#wdkgloss.exception"><i>exception</i></a>debugging event occurs in the target.



## -syntax

````
HRESULT Exception(
  [in] PEXCEPTION_RECORD64 Exception,
  [in] ULONG               FirstChance
);
````


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

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.</p>