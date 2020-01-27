---
UID: NF:dbgeng.IDebugEventCallbacks.UnloadModule
title: IDebugEventCallbacks::UnloadModule (dbgeng.h)
description: The UnloadModule callback method is called by the engine when a module-unload debugging event occurs in the target.
old-location: debugger\idebugeventcallbacks_unloadmodule.htm
tech.root: debugger
ms.assetid: 2afdaee6-7714-42d4-a402-3cb85ef3b970
ms.date: 05/03/2018
ms.keywords: ComCallbacks_53674f8e-290c-44d6-827f-92646c2e4ea9.xml, IDebugEventCallbacks interface [Windows Debugging],UnloadModule method, IDebugEventCallbacks.UnloadModule, IDebugEventCallbacks::UnloadModule, UnloadModule, UnloadModule method [Windows Debugging], UnloadModule method [Windows Debugging],IDebugEventCallbacks interface, dbgeng/IDebugEventCallbacks::UnloadModule, debugger.idebugeventcallbacks_unloadmodule
f1_keywords:
 - "dbgeng/IDebugEventCallbacks.UnloadModule"
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
- IDebugEventCallbacks.UnloadModule
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugEventCallbacks::UnloadModule


## -description


The <b>UnloadModule</b> callback method is called by the engine when a module-unload debugging event occurs in the target.


## -parameters




### -param ImageBaseName [in, optional]

Specifies the name of the module's image file, which can include the path.  If this information is not available, <i>ImageBaseName</i> will be <b>NULL</b>.


### -param BaseOffset [in]

Specifies the base address of the module in the target's memory address space.    If this information is not available, <i>BaseOffset</i> will be <b>NULL</b>.


## -returns



This method returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-status-xxx">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/monitoring-events">Monitoring Events</a>.




## -remarks



This method is only called by the engine if the DEBUG_EVENT_UNLOAD_MODULE flag is set in the mask returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-getinterestmask">IDebugEventCallbacks::GetInterestMask</a>.

After calling this method, the engine will call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-changesymbolstate">IDebugEventCallbacks::ChangeSymbolState</a>, with the <i>Flags</i> parameter containing the bit flag DEBUG_CSS_UNLOADS.

For more information about handling events, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/monitoring-events">Monitoring Events</a>.



