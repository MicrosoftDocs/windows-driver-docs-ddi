---
UID: NF:dbgeng.IDebugEventCallbacksWide.SystemError
title: IDebugEventCallbacksWide::SystemError (dbgeng.h)
description: The SystemError callback method is called by the engine when a system error occurs in the target.
old-location: debugger\idebugeventcallbackswide_systemerror.htm
tech.root: debugger
ms.assetid: 938eacb5-7939-43ed-a854-046708fc9c79
ms.date: 05/03/2018
ms.keywords: IDebugEventCallbacksWide interface [Windows Debugging],SystemError method, IDebugEventCallbacksWide.SystemError, IDebugEventCallbacksWide::SystemError, SystemError, SystemError method [Windows Debugging], SystemError method [Windows Debugging],IDebugEventCallbacksWide interface, dbgeng/IDebugEventCallbacksWide::SystemError, debugger.idebugeventcallbackswide_systemerror
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
- IDebugEventCallbacksWide.SystemError
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugEventCallbacksWide::SystemError


## -description


The <b>SystemError</b> callback method is called by the engine when a system error occurs in the target.


## -parameters




### -param Error [in]

Specifies the error that caused the event.


### -param Level [in]

Specifies the severity of the error.


## -returns



This method returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-status-xxx">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/monitoring-events">Monitoring Events</a>.




## -remarks



This method is only called by the engine if the DEBUG_EVENT_SYSTEM_ERROR flag is set in the mask returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbackswide-getinterestmask">IDebugEventCallbacksWide::GetInterestMask</a>.

For more information about handling events, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/monitoring-events">Monitoring Events</a>.



