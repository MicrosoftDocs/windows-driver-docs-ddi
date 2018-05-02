---
UID: NN:dbgeng.IDebugInputCallbacks
title: IDebugInputCallbacks
author: windows-driver-content
description: IDebugInputCallbacks interface
old-location: debugger\idebuginputcallbacks.htm
old-project: debugger
ms.assetid: 2122d970-1d1c-4ef0-b8f7-92ef6e4f0731
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: ComCallbacks_9dd6d3d2-e92d-41bc-8276-fa8b7818a372.xml, IDebugInputCallbacks, IDebugInputCallbacks interface [Windows Debugging], IDebugInputCallbacks interface [Windows Debugging],described, dbgeng/IDebugInputCallbacks, debugger.idebuginputcallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugInputCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugInputCallbacks interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugInputCallbacks</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IDebugInputCallbacks</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugInputCallbacks</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/e22b616c-51f6-4687-95b0-eb833ceb9ec3">EndInput</a>
</td>
<td align="left" width="63%">
This method is called by the engine to indicate that it is no longer waiting for input.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/4ac3764e-6482-49de-aac8-3b540561d201">StartInput</a>
</td>
<td align="left" width="63%">
This method is called by the engine to indicate that it is waiting for a line of input.


</td>
</tr>
</table> 

