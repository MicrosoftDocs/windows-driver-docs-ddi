---
UID: NF:dbgeng.IDebugEventCallbacks.UnloadModule
title: IDebugEventCallbacks::UnloadModule
author: windows-driver-content
description: The UnloadModule callback method is called by the engine when a module-unload debugging event occurs in the target.
old-location: debugger\idebugeventcallbacks_unloadmodule.htm
old-project: debugger
ms.assetid: 2afdaee6-7714-42d4-a402-3cb85ef3b970
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: ComCallbacks_53674f8e-290c-44d6-827f-92646c2e4ea9.xml, IDebugEventCallbacks interface [Windows Debugging],UnloadModule method, IDebugEventCallbacks.UnloadModule, IDebugEventCallbacks::UnloadModule, UnloadModule, UnloadModule method [Windows Debugging], UnloadModule method [Windows Debugging],IDebugEventCallbacks interface, dbgeng/IDebugEventCallbacks::UnloadModule, debugger.idebugeventcallbacks_unloadmodule
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
-	IDebugEventCallbacks.UnloadModule
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



This method returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.




## -remarks



This method is only called by the engine if the DEBUG_EVENT_UNLOAD_MODULE flag is set in the mask returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550737">IDebugEventCallbacks::GetInterestMask</a>.

After calling this method, the engine will call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550692">IDebugEventCallbacks::ChangeSymbolState</a>, with the <i>Flags</i> parameter containing the bit flag DEBUG_CSS_UNLOADS.

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.



