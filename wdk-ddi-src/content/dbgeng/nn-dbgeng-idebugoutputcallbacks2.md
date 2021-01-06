---
UID: NN:dbgeng.IDebugOutputCallbacks2
title: IDebugOutputCallbacks2 (dbgeng.h)
description: The IDebugOutputCallbacks2 interface allows clients to receive full debugger markup language (DML) content for presentation.
old-location: debugger\idebugoutputcallbacks2.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugOutputCallbacks2 interface"]
ms.keywords: IDebugOutputCallbacks2, IDebugOutputCallbacks2 interface [Windows Debugging], IDebugOutputCallbacks2 interface [Windows Debugging],described, dbgeng/IDebugOutputCallbacks2, debugger.idebugoutputcallbacks2
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
 - IDebugOutputCallbacks2
 - dbgeng/IDebugOutputCallbacks2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugOutputCallbacks2
---

# IDebugOutputCallbacks2 interface


## -description

The <b>IDebugOutputCallbacks2</b> interface allows clients to receive full  debugger markup language (DML) content for presentation. 

This interface extends the <a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbacks">IDebugOutputCallbacks</a> interface, not the <a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbackswide">IDebugOutputCallbacksWide</a> interface. Therefore, it can be passed in to the existing <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-setoutputcallbacks">SetOutputCallbacks</a> method. 

The engine performs a <b>QueryInterface</b> for <b>IDebugOutputCallbacks2</b> to see which interface the incoming output callback object supports. If the object supports <b>IDebugOutputCallbacks2</b>, all output will be sent through the extended <b>IDebugOutputCallbacks2</b> methods.

An output object can register for both text and DML content, if it can handle them both. During output processing of the callback the engine will pick the format that reduces conversions, thus supporting both may reduce conversions in the engine. It is not necessary, though, and supporting only one format is the expected mode of operation.

The basic <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugoutputcallbacks-output">IDebugOutputCallbacks::Output</a> method is not used.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugOutputCallbacks2</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IDebugOutputCallbacks2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbacks">IDebugOutputCallbacks</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbackswide">IDebugOutputCallbacksWide</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-setoutputcallbacks">SetOutputCallbacks</a>
