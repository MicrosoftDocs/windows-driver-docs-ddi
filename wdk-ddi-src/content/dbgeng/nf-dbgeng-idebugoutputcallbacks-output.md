---
UID: NF:dbgeng.IDebugOutputCallbacks.Output
title: IDebugOutputCallbacks::Output (dbgeng.h)
description: The Output callback method is called by the engine to send output from the client to the IDebugOutputCallbacks object that is registered with the client.
old-location: debugger\idebugoutputcallbacks_output.htm
tech.root: debugger
ms.assetid: 6d0352ae-0376-4992-89ef-90702591042e
ms.date: 05/03/2018
ms.keywords: ComCallbacks_9b5e22d8-aa8d-498e-b3b5-ad6d73462db4.xml, IDebugOutputCallbacks interface [Windows Debugging],Output method, IDebugOutputCallbacks.Output, IDebugOutputCallbacks::Output, Output, Output method [Windows Debugging], Output method [Windows Debugging],IDebugOutputCallbacks interface, dbgeng/IDebugOutputCallbacks::Output, debugger.idebugoutputcallbacks_output
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
- IDebugOutputCallbacks.Output
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugOutputCallbacks::Output


## -description


The <b>Output</b> callback method is called by the engine to send output from the client to the <b>IDebugOutputCallbacks</b>  object that is registered with the client.


## -parameters




### -param Mask [in]

Specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-output-xxx">DEBUG_OUTPUT_XXX</a> bit flags that indicate the nature of the output.


### -param Text [in]

Specifies the output that is being sent.


## -returns



The return value is ignored by the engine unless it indicates a remote procedure call error; in this case the client, with which this <b>IDebugEventCallbacks</b> object is registered, is disabled.




## -remarks



The engine calls this method only if the supplied value of <i>Mask</i> is allowed by the client's output control.

For more information about debugger engine output, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/input-and-output">Input and Output</a>.



