---
UID: NN:dbgeng.IDebugOutputCallbacksWide
title: IDebugOutputCallbacksWide (dbgeng.h)
description: IDebugOutputCallbacksWide interface
old-location: debugger\idebugoutputcallbackswide.htm
tech.root: debugger
ms.assetid: 2f0c10f7-009a-4108-ad23-d6b6e2e1257e
ms.date: 05/03/2018
ms.keywords: IDebugOutputCallbacksWide, IDebugOutputCallbacksWide interface [Windows Debugging], IDebugOutputCallbacksWide interface [Windows Debugging],described, dbgeng/IDebugOutputCallbacksWide, debugger.idebugoutputcallbackswide
ms.topic: interface
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugOutputCallbacksWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugOutputCallbacksWide interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugOutputCallbacksWide</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IDebugOutputCallbacksWide</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugOutputCallbacksWide</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553183">Output</a>
</td>
<td align="left" width="63%">
This method is called by the engine to send output from the client to the <b>IDebugOutputCallbacksWide</b> object that is registered with the client.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugoutputcallbacks">IDebugOutputCallbacks</a>
 

 

