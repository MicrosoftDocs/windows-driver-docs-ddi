---
UID: NF:dbgeng.IDebugOutputCallbacksWide.Output
title: IDebugOutputCallbacksWide::Output
description: The Output callback method is called by the engine to send output from the client to the IDebugOutputCallbacksWide object that is registered with the client.
old-location: debugger\idebugoutputcallbackswide_output.htm
tech.root: debugger
ms.assetid: b57661c3-a18f-45ed-b7fc-f6471753566e
ms.date: 05/03/2018
ms.keywords: IDebugOutputCallbacksWide interface [Windows Debugging],Output method, IDebugOutputCallbacksWide.Output, IDebugOutputCallbacksWide::Output, Output, Output method [Windows Debugging], Output method [Windows Debugging],IDebugOutputCallbacksWide interface, dbgeng/IDebugOutputCallbacksWide::Output, debugger.idebugoutputcallbackswide_output
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
-	IDebugOutputCallbacksWide.Output
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugOutputCallbacksWide::Output


## -description


The <b>Output</b> callback method is called by the engine to send output from the client to the  <b>IDebugOutputCallbacksWide</b> object that is registered with the client.


## -parameters




### -param Mask [in]

Specifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541518">DEBUG_OUTPUT_XXX</a> bit flags that indicate the nature of the output.


### -param Text [in]

Specifies the output that is being sent.


## -returns



The return value is ignored by the engine unless it indicates a remote procedure call error; in this case the client, with which this <b>IDebugEventCallbacksWide</b> object is registered, is disabled.




## -remarks



The engine calls this method only if the supplied value of <i>Mask</i> is allowed by the client's output control.

For more information about debugger engine output, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.



