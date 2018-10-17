---
UID: NL:dbgeng.DebugBaseEventCallbacks
title: DebugBaseEventCallbacks
author: windows-driver-content
description: The DebugBaseEventCallbacks class provides a base implementation of the IDebugEventCallbacks interface.
old-location: debugger\debugbaseeventcallbacks.htm
tech.root: debugger
ms.assetid: B0422248-2F5F-4AE6-93C9-D96B5E4A1B5A
ms.date: 5/3/2018
ms.keywords: DebugBaseEventCallbacks, DebugBaseEventCallbacks class [Windows Debugging], DebugBaseEventCallbacks class [Windows Debugging],described, dbgeng/DebugBaseEventCallbacks, debugger.debugbaseeventcallbacks
ms.topic: class
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
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
-	DebugBaseEventCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# DebugBaseEventCallbacks class


## -description


The <b>DebugBaseEventCallbacks</b> class provides a base implementation
of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550550">IDebugEventCallbacks</a> interface.  

A program can derive an event callbacks class from <b>DebugBaseEventCallbacks</b> and implement
only the methods needed. 

Be careful to implement <a href="https://msdn.microsoft.com/165c83cb-c0be-4a09-9220-a5208f660308">GetInterestMask</a> appropriately.


## -see-also




<a href="https://msdn.microsoft.com/165c83cb-c0be-4a09-9220-a5208f660308">GetInterestMask</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550550">IDebugEventCallbacks</a>
 

 

