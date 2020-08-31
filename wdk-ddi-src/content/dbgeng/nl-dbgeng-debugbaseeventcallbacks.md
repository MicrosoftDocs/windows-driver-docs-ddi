---
UID: NL:dbgeng.DebugBaseEventCallbacks
title: DebugBaseEventCallbacks (dbgeng.h)
description: The DebugBaseEventCallbacks class provides a base implementation of the IDebugEventCallbacks interface.
old-location: debugger\debugbaseeventcallbacks.htm
tech.root: debugger
ms.assetid: B0422248-2F5F-4AE6-93C9-D96B5E4A1B5A
ms.date: 05/03/2018
keywords: ["DebugBaseEventCallbacks class"]
ms.keywords: DebugBaseEventCallbacks, DebugBaseEventCallbacks class [Windows Debugging], DebugBaseEventCallbacks class [Windows Debugging],described, dbgeng/DebugBaseEventCallbacks, debugger.debugbaseeventcallbacks
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
targetos: Windows
req.typenames: 
f1_keywords:
 - DebugBaseEventCallbacks
 - dbgeng/DebugBaseEventCallbacks
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - DebugBaseEventCallbacks
---

# DebugBaseEventCallbacks class


## -description

The <b>DebugBaseEventCallbacks</b> class provides a base implementation
of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugeventcallbacks">IDebugEventCallbacks</a> interface.  

A program can derive an event callbacks class from <b>DebugBaseEventCallbacks</b> and implement
only the methods needed. 

Be careful to implement <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-getinterestmask">GetInterestMask</a> appropriately.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-getinterestmask">GetInterestMask</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugeventcallbacks">IDebugEventCallbacks</a>

