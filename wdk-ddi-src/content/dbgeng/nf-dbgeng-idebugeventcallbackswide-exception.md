---
UID: NF:dbgeng.IDebugEventCallbacksWide.Exception
title: IDebugEventCallbacksWide::Exception (dbgeng.h)
description: The Exception callback method is called by the engine when an exceptiondebugging event occurs in the target.
old-location: debugger\idebugeventcallbackswide_exception.htm
tech.root: debugger
ms.assetid: 02f5bec1-f2d2-4b72-bd9e-b30315c334da
ms.date: 05/03/2018
ms.keywords: Exception, Exception method [Windows Debugging], Exception method [Windows Debugging],IDebugEventCallbacksWide interface, IDebugEventCallbacksWide interface [Windows Debugging],Exception method, IDebugEventCallbacksWide.Exception, IDebugEventCallbacksWide::Exception, dbgeng/IDebugEventCallbacksWide::Exception, debugger.idebugeventcallbackswide_exception
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugEventCallbacksWide.Exception"
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
- IDebugEventCallbacksWide.Exception
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugEventCallbacksWide::Exception


## -description


The <b>Exception</b> callback method is called by the engine when an <a href="https://docs.microsoft.com/windows-hardware/drivers/">exception</a>debugging event occurs in the target.


## -parameters




### -param Exception [in]

Specifies the nature of the exception.  EXCEPTION_RECORD64 is defined in Winnt.h.


### -param FirstChance [in]

Specifies whether this exception has been previously encountered.  A nonzero value means that this is the first time the exception has been encountered ("first chance").  A zero value means that the exception has already been offered to all possible handlers, and each one declined to handle it ("second chance").


## -returns



This method returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-status-xxx">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/monitoring-events">Monitoring Events</a>.




## -remarks



This method is only called by the engine if the DEBUG_EVENT_EXCEPTION flag is set in the mask returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbackswide-getinterestmask">IDebugEventCallbacksWide::GetInterestMask</a>.

Because the structure that <i>Exception</i> points to might be deleted after this method returns, implementations of <b>IDebugEventCallbacksWide</b> should not access this structure after returning.

For more information about handling events, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/monitoring-events">Monitoring Events</a>.



