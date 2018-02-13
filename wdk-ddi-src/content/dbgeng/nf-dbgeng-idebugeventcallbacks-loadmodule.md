---
UID: NF:dbgeng.IDebugEventCallbacks.LoadModule
title: IDebugEventCallbacks::LoadModule method
author: windows-driver-content
description: The LoadModule callback method is called by the engine when a module-load debugging event occurs in the target.
old-location: debugger\idebugeventcallbacks_loadmodule.htm
old-project: debugger
ms.assetid: f4efcbf3-f78a-4e0e-9741-4f9b68814e5b
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugEventCallbacks::LoadModule, IDebugEventCallbacks, LoadModule method [Windows Debugging], LoadModule method [Windows Debugging], IDebugEventCallbacks interface, IDebugEventCallbacks interface [Windows Debugging], LoadModule method, ComCallbacks_3d8f0501-0915-425e-a940-aa5f41bad734.xml, dbgeng/IDebugEventCallbacks::LoadModule, debugger.idebugeventcallbacks_loadmodule, LoadModule
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
-	IDebugEventCallbacks.LoadModule
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugEventCallbacks::LoadModule method


## -description


The <b>LoadModule</b> callback method is called by the engine when a module-load debugging event occurs in the target.


## -syntax


````
HRESULT LoadModule(
  [in]           ULONG64 ImageFileHandle,
  [in]           ULONG64 BaseOffset,
  [in]           ULONG   ModuleSize,
  [in, optional] PCSTR   ModuleName,
  [in, optional] PCSTR   ImageName,
  [in]           ULONG   CheckSum,
  [in]           ULONG   TimeDateStamp
);
````


## -parameters




### -param ImageFileHandle [in]

Specifies the handle to the module's image file.  If this information is not available, <i>ImageFileHandle</i> will be <b>NULL</b>. 


### -param BaseOffset [in]

Specifies the base address of the module in the target's memory address space.  If this information is not available, <i>BaseOffset</i> will be <b>NULL</b>.


### -param ModuleSize [in]

Specifies the module's image size in bytes.  If this information is not available, <i>ModuleSize</i> will be <b>NULL</b>.


### -param ModuleName [in, optional]

Specifies the simplified module name that is used by the debugger engine.  In most cases, this matches the image file name excluding the extension.  If this information is not available, <i>ModuleName</i> will be <b>NULL</b>.


### -param ImageName [in, optional]

Specifies the module's image file name, which can include the path.  If this information is not available, <i>ImageName</i> will be <b>NULL</b>.


### -param CheckSum [in]

Specifies the checksum of the module's image file.  If this information is not available, <i>CheckSum</i> will be <b>NULL</b>.


### -param TimeDateStamp [in]

Specifies the time and date stamp of the module's image file.  If this information is not available, <i>TimeDateStamp</i> will be zero.


## -returns



This method returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.




## -remarks



This method is only called by the engine if the DEBUG_EVENT_LOAD_MODULE flag is set in the mask returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550737">IDebugEventCallbacks::GetInterestMask</a>.

After calling this method, the engine will call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550692">IDebugEventCallbacks::ChangeSymbolState</a>, with the <i>Flags</i> parameter containing the bit flag DEBUG_CSS_LOADS.

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>. 



