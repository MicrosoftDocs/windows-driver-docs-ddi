---
UID: NF:dbgeng.IDebugInputCallbacks.EndInput
title: IDebugInputCallbacks::EndInput (dbgeng.h)
description: The EndInput callback method is called by the engine to indicate that it is no longer waiting for input.
old-location: debugger\idebuginputcallbacks_endinput.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugInputCallbacks::EndInput"]
ms.keywords: ComCallbacks_3e06dd1c-483b-4934-83d5-b00241d9d88b.xml, EndInput, EndInput method [Windows Debugging], EndInput method [Windows Debugging],IDebugInputCallbacks interface, IDebugInputCallbacks interface [Windows Debugging],EndInput method, IDebugInputCallbacks.EndInput, IDebugInputCallbacks::EndInput, dbgeng/IDebugInputCallbacks::EndInput, debugger.idebuginputcallbacks_endinput
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugInputCallbacks::EndInput
 - dbgeng/IDebugInputCallbacks::EndInput
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugInputCallbacks::EndInput
---

# IDebugInputCallbacks::EndInput


## -description

The <b>EndInput</b> callback method is called by the engine to indicate that it is no longer waiting for input.

## -returns

This method's return value is ignored by the engine.

## -remarks

Even if the engine has not called <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebuginputcallbacks-startinput">IDebugInputCallbacks::StartInput</a> for this <a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebuginputcallbacks">IDebugInputCallbacks</a> object, the engine will call <b>EndInput</b> if another IDebugInputCallbacks object returned an error from the <b>IDebugInputCallbacks::StartInput</b> method.

For more information about debugger engine input, see <a href="/windows-hardware/drivers/debugger/input-and-output">Input and Output</a>.

