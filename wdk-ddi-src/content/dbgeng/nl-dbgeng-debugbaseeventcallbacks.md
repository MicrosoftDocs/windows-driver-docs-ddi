---
UID: NL:dbgeng.DebugBaseEventCallbacks
title: DebugBaseEventCallbacks
author: windows-driver-content
description: The DebugBaseEventCallbacks class provides a base implementation of the IDebugEventCallbacks interface.
old-location: debugger\debugbaseeventcallbacks.htm
old-project: debugger
ms.assetid: B0422248-2F5F-4AE6-93C9-D96B5E4A1B5A
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.debugbaseeventcallbacks, DebugBaseEventCallbacks class [Windows Debugging], DebugBaseEventCallbacks class [Windows Debugging], described, DebugBaseEventCallbacks, dbgeng/DebugBaseEventCallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	DebugBaseEventCallbacks
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETENCRYPTIONBLTKEY
---

# DebugBaseEventCallbacks class


## -description


The <b>DebugBaseEventCallbacks</b> class provides a base implementation
of the <a href="..\dbgeng\nn-dbgeng-idebugeventcallbacks.md">IDebugEventCallbacks</a> interface.  

A program can derive an event callbacks class from <b>DebugBaseEventCallbacks</b> and implement
only the methods needed. 

Be careful to implement <a href="https://msdn.microsoft.com/165c83cb-c0be-4a09-9220-a5208f660308">GetInterestMask</a> appropriately.


## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugeventcallbacks.md">IDebugEventCallbacks</a>

<a href="https://msdn.microsoft.com/165c83cb-c0be-4a09-9220-a5208f660308">GetInterestMask</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20DebugBaseEventCallbacks class%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

