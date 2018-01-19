---
UID: NF:dbgeng.IDebugInputCallbacks.EndInput
title: IDebugInputCallbacks::EndInput method
author: windows-driver-content
description: The EndInput callback method is called by the engine to indicate that it is no longer waiting for input.
old-location: debugger\idebuginputcallbacks_endinput.htm
old-project: debugger
ms.assetid: e22b616c-51f6-4687-95b0-eb833ceb9ec3
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugInputCallbacks, IDebugInputCallbacks::EndInput, EndInput
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
req.alt-api: IDebugInputCallbacks.EndInput
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

# IDebugInputCallbacks::EndInput method



## -description
The <b>EndInput</b> callback method is called by the engine to indicate that it is no longer waiting for input.



## -syntax

````
HRESULT EndInput();
````


## -parameters


## -returns
This method's return value is ignored by the engine.

This method's return value is ignored by the engine.

This method's return value is ignored by the engine.


## -remarks
Even if the engine has not called <a href="https://msdn.microsoft.com/library/windows/hardware/ff550797">IDebugInputCallbacks::StartInput</a> for this <a href="..\dbgeng\nn-dbgeng-idebuginputcallbacks.md">IDebugInputCallbacks</a> object, the engine will call <b>EndInput</b> if another IDebugInputCallbacks object returned an error from the <b>IDebugInputCallbacks::StartInput</b> method.

For more information about debugger engine input, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.</p>