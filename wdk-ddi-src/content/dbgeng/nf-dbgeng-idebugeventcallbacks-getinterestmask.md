---
UID: NF:dbgeng.IDebugEventCallbacks.GetInterestMask
title: IDebugEventCallbacks::GetInterestMask method
author: windows-driver-content
description: The GetInterestMask callback method is called to determine which events the IDebugEventCallbacks object is interested in. The engine calls GetInterestMask when the object is registered with a client by using SetEventCallbacks.
old-location: debugger\idebugeventcallbacks_getinterestmask.htm
old-project: debugger
ms.assetid: 165c83cb-c0be-4a09-9220-a5208f660308
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugEventCallbacks interface [Windows Debugging], GetInterestMask method, IDebugEventCallbacks, GetInterestMask method [Windows Debugging], IDebugEventCallbacks interface, GetInterestMask, GetInterestMask method [Windows Debugging], IDebugEventCallbacks::GetInterestMask, ComCallbacks_564e7fce-ee9a-404e-9ae4-06805cb0b677.xml, dbgeng/IDebugEventCallbacks::GetInterestMask, debugger.idebugeventcallbacks_getinterestmask
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
-	IDebugEventCallbacks.GetInterestMask
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugEventCallbacks::GetInterestMask method


## -description


The <b>GetInterestMask</b> callback method is called to determine which <a href="https://msdn.microsoft.com/library/windows/hardware/ff543067">events</a> the <b>IDebugEventCallbacks</b> object is interested in.  The engine calls <b>GetInterestMask</b> when the object is registered with a client by using <a href="https://msdn.microsoft.com/library/windows/hardware/ff556671">SetEventCallbacks</a>.


## -syntax


````
HRESULT GetInterestMask(
  [out] PULONG Mask
);
````


## -parameters




### -param Mask [out]

Receives a bitmask that indicates which events the object is interested in.  The engine will call only those methods that correspond to the bit flags set by <b>GetInterestMask</b>.  For a description of the bit flags and their corresponding methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541478">DEBUG_EVENT_XXX</a>.


## -returns


The return value S_OK indicates the method was successful.  All other return values indicate an error occurred,  in which case the <b>SetEventCallbacks</b> call will fail and the callback object will not be used nor will it receive events.



## -remarks


For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.


