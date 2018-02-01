---
UID: NF:dbgeng.IDebugEventCallbacks.ChangeSymbolState
title: IDebugEventCallbacks::ChangeSymbolState method
author: windows-driver-content
description: The ChangeSymbolState callback method is called by the engine when the symbol state changes.
old-location: debugger\idebugeventcallbacks_changesymbolstate.htm
old-project: debugger
ms.assetid: 5383bd49-df44-48dd-8385-c782a1b1f80a
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: ComCallbacks_693f0465-088e-4f3d-a8a4-89e8803d0227.xml, ChangeSymbolState method [Windows Debugging], IDebugEventCallbacks interface, IDebugEventCallbacks, ChangeSymbolState method [Windows Debugging], debugger.idebugeventcallbacks_changesymbolstate, dbgeng/IDebugEventCallbacks::ChangeSymbolState, IDebugEventCallbacks interface [Windows Debugging], ChangeSymbolState method, IDebugEventCallbacks::ChangeSymbolState, ChangeSymbolState
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
-	IDebugEventCallbacks.ChangeSymbolState
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugEventCallbacks::ChangeSymbolState method


## -description


The <b>ChangeSymbolState</b> callback method is called by the engine when the symbol state changes. 


## -syntax


````
HRESULT ChangeSymbolState(
  [in] ULONG   Flags,
  [in] ULONG64 Argument
);
````


## -parameters




### -param Flags [in]

Specifies a bit-set indicating the nature of the change to the symbol state.  The following bit flags might be set.
<table>
<tr>
<th>Value</th>
<th>Description </th>
</tr>
<tr>
<td>
DEBUG_CSS_LOADS

</td>
<td>
The engine has loaded some module symbols.

</td>
</tr>
<tr>
<td>
DEBUG_CSS_UNLOADS

</td>
<td>
The engine has unloaded some module symbols.

</td>
</tr>
<tr>
<td>
DEBUG_CSS_SCOPE

</td>
<td>
The current symbol scope has changed.

</td>
</tr>
<tr>
<td>
DEBUG_CSS_PATHS

</td>
<td>
The executable image, source , or symbol search paths have changed.

</td>
</tr>
<tr>
<td>
DEBUG_CSS_SYMBOL_OPTIONS

</td>
<td>
The symbol options have changed.

</td>
</tr>
<tr>
<td>
DEBUG_CSS_TYPE_OPTIONS

</td>
<td>
The type options have changed.

</td>
</tr>
</table> 


### -param Argument [in]

Provides additional information about the change to the symbol state.   If more than one bit flag is set in the <i>Flags</i> parameter, the <i>Argument</i> parameter is not used.  Otherwise, the value of <i>Argument</i> depends on the value of <i>Flags</i>:




#### DEBUG_CSS_LOADS

The value of <i>Argument</i> is the base location (in the target's memory address space) of the module image that the engine loaded symbols for.


#### DEBUG_CSS_PATHS

The value of <i>Argument</i> is zero.


#### DEBUG_CSS_SCOPE

The value of <i>Argument</i> is zero.


#### DEBUG_CSS_SYMBOL_OPTIONS

The value of <i>Argument</i> is the symbol options.


#### DEBUG_CSS_TYPE_OPTIONS

The value of <i>Argument</i> is zero.


#### DEBUG_CSS_UNLOADS

The value of <i>Argument</i> is the base location (in the target's memory address space) of the module image that the engine unloaded symbols for.  If the engine unloaded symbols for more than one image, the value of <i>Argument</i> is zero.


## -returns


The return value is ignored by the engine unless it indicates a remote procedure call error; in this case the client, with which this <b>IDebugEventCallbacks</b> object is registered, is disabled.



## -remarks


This method is only called by the engine if the DEBUG_EVENT_CHANGE_SYMBOL_STATE flag is set in the mask returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550737">IDebugEventCallbacks::GetInterestMask</a>.

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>. 


