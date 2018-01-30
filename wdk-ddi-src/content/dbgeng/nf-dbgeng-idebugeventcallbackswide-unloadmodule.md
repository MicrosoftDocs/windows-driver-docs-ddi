---
UID: NF:dbgeng.IDebugEventCallbacksWide.UnloadModule
title: IDebugEventCallbacksWide::UnloadModule method
author: windows-driver-content
description: The UnloadModule callback method is called by the engine when a module-unload debugging event occurs in the target.
old-location: debugger\idebugeventcallbackswide_unloadmodule.htm
old-project: debugger
ms.assetid: 05f3fa93-389e-4ecc-b7c0-71f43691232f
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: UnloadModule method [Windows Debugging], IDebugEventCallbacksWide interface, UnloadModule method [Windows Debugging], dbgeng/IDebugEventCallbacksWide::UnloadModule, IDebugEventCallbacksWide, UnloadModule, IDebugEventCallbacksWide interface [Windows Debugging], UnloadModule method, IDebugEventCallbacksWide::UnloadModule, debugger.idebugeventcallbackswide_unloadmodule
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugEventCallbacksWide.UnloadModule
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugEventCallbacksWide::UnloadModule method


## -description


The <b>UnloadModule</b> callback method is called by the engine when a module-unload debugging event occurs in the target.


## -syntax


````
HRESULT UnloadModule(
  [in, optional] PCWSTR  ImageBaseName,
  [in]           ULONG64 BaseOffset
);
````


## -parameters




### -param ImageBaseName [in, optional]

Specifies the name of the module's image file, which can include the path.  If this information is not available, <i>ImageBaseName</i> will be <b>NULL</b>.


### -param BaseOffset [in]

Specifies the base address of the module in the target's memory address space.    If this information is not available, <i>BaseOffset</i> will be <b>NULL</b>.


## -returns


This method returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.



## -remarks


This method is only called by the engine if the DEBUG_EVENT_UNLOAD_MODULE flag is set in the mask returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550625">IDebugEventCallbacksWide::GetInterestMask</a>.

After calling this method, the engine will call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550587">IDebugEventCallbacksWide::ChangeSymbolState</a>, with the <i>Flags</i> parameter containing the bit flag DEBUG_CSS_UNLOADS.

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.


