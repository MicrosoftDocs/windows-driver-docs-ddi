---
UID: NF:dbgeng.IDebugOutputCallbacksWide.Output
title: IDebugOutputCallbacksWide::Output method
author: windows-driver-content
description: The Output callback method is called by the engine to send output from the client to the IDebugOutputCallbacksWide object that is registered with the client.
old-location: debugger\idebugoutputcallbackswide_output.htm
old-project: debugger
ms.assetid: b57661c3-a18f-45ed-b7fc-f6471753566e
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.idebugoutputcallbackswide_output, dbgeng/IDebugOutputCallbacksWide::Output, Output method [Windows Debugging], IDebugOutputCallbacksWide interface, IDebugOutputCallbacksWide interface [Windows Debugging], Output method, Output, Output method [Windows Debugging], IDebugOutputCallbacksWide, IDebugOutputCallbacksWide::Output
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
-	IDebugOutputCallbacksWide.Output
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugOutputCallbacksWide::Output method


## -description


The <b>Output</b> callback method is called by the engine to send output from the client to the  <b>IDebugOutputCallbacksWide</b> object that is registered with the client.


## -syntax


````
HRESULT Output(
  [in] ULONG  Mask,
  [in] PCWSTR Text
);
````


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


