---
UID: NN:dbgeng.IDebugOutputCallbacks2
title: IDebugOutputCallbacks2 (dbgeng.h)
description: The IDebugOutputCallbacks2 interface allows clients to receive full debugger markup language (DML) content for presentation.
old-location: debugger\idebugoutputcallbacks2.htm
tech.root: debugger
ms.assetid: D35D8960-AD9F-4493-B6CD-3E3049CC3BBD
ms.date: 05/03/2018
ms.keywords: IDebugOutputCallbacks2, IDebugOutputCallbacks2 interface [Windows Debugging], IDebugOutputCallbacks2 interface [Windows Debugging],described, dbgeng/IDebugOutputCallbacks2, debugger.idebugoutputcallbacks2
ms.topic: interface
f1_keywords:
 - "dbgeng/IDebugOutputCallbacks2"
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
- IDebugOutputCallbacks2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugOutputCallbacks2 interface


## -description


The <b>IDebugOutputCallbacks2</b> interface allows clients to receive full  debugger markup language (DML) content for presentation. 

This interface extends the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbacks">IDebugOutputCallbacks</a> interface, not the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbackswide">IDebugOutputCallbacksWide</a> interface. Therefore, it can be passed in to the existing <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-setoutputcallbacks">SetOutputCallbacks</a> method. 

The engine performs a <b>QueryInterface</b> for <b>IDebugOutputCallbacks2</b> to see which interface the incoming output callback object supports. If the object supports <b>IDebugOutputCallbacks2</b>, all output will be sent through the extended <b>IDebugOutputCallbacks2</b> methods.

An output object can register for both text and DML content, if it can handle them both. During output processing of the callback the engine will pick the format that reduces conversions, thus supporting both may reduce conversions in the engine. It is not necessary, though, and supporting only one format is the expected mode of operation.

The basic <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugoutputcallbacks-output">IDebugOutputCallbacks::Output</a> method is not used. 


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugOutputCallbacks2</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IDebugOutputCallbacks2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugOutputCallbacks2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugoutputcallbacks2-getinterestmask">GetInterestMask</a>
</td>
<td align="left" width="63%">
Allows the callback object to describe which kinds of output notifications it wants to receive. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553183">Output</a>
</td>
<td align="left" width="63%">
This method is not used.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugoutputcallbacks2-output2">Output2</a>
</td>
<td align="left" width="63%">
Returns notifications for the <b>IDebugOutputCallbacks2</b> interface.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbacks">IDebugOutputCallbacks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbackswide">IDebugOutputCallbacksWide</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-setoutputcallbacks">SetOutputCallbacks</a>
 

 

