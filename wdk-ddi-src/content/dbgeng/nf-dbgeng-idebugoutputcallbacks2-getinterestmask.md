---
UID: NF:dbgeng.IDebugOutputCallbacks2.GetInterestMask
title: IDebugOutputCallbacks2::GetInterestMask (dbgeng.h)
description: Allows the callback object to describe which kinds of output notifications it wants to receive.
old-location: debugger\idebugoutputcallbacks2_getinterestmask.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugOutputCallbacks2::GetInterestMask"]
ms.keywords: DEBUG_OUTCBI_ANY_FORMAT, DEBUG_OUTCBI_DML, DEBUG_OUTCBI_EXPLICIT_FLUSH, DEBUG_OUTCBI_TEXT, GetInterestMask, GetInterestMask method [Windows Debugging], GetInterestMask method [Windows Debugging],IDebugOutputCallbacks2 interface, IDebugOutputCallbacks2 interface [Windows Debugging],GetInterestMask method, IDebugOutputCallbacks2.GetInterestMask, IDebugOutputCallbacks2::GetInterestMask, dbgeng/IDebugOutputCallbacks2::GetInterestMask, debugger.idebugoutputcallbacks2_getinterestmask
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
 - IDebugOutputCallbacks2::GetInterestMask
 - dbgeng/IDebugOutputCallbacks2::GetInterestMask
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugOutputCallbacks2.GetInterestMask
---

# IDebugOutputCallbacks2::GetInterestMask


## -description

Allows the callback object to describe which kinds of output notifications it wants to receive.

## -parameters

### -param Mask

The type of output notification to receive. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="DEBUG_OUTCBI_EXPLICIT_FLUSH"></a><a id="debug_outcbi_explicit_flush"></a><dl>
<dt><b>DEBUG_OUTCBI_EXPLICIT_FLUSH</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%">
Indicates that the callback wants notifications
of all explicit flushes.

</td>
</tr>
<tr>
<td width="40%"><a id="DEBUG_OUTCBI_TEXT"></a><a id="debug_outcbi_text"></a><dl>
<dt><b>DEBUG_OUTCBI_TEXT</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
Indicates that the callback wants
content in text form.

</td>
</tr>
<tr>
<td width="40%"><a id="DEBUG_OUTCBI_DML"></a><a id="debug_outcbi_dml"></a><dl>
<dt><b>DEBUG_OUTCBI_DML</b></dt>
<dt>0x00000004
</dt>
</dl>
</td>
<td width="60%">
Indicates that the callback wants
content in markup form.

</td>
</tr>
<tr>
<td width="40%"><a id="DEBUG_OUTCBI_ANY_FORMAT"></a><a id="debug_outcbi_any_format"></a><dl>
<dt><b>DEBUG_OUTCBI_ANY_FORMAT</b></dt>
<dt>0x00000006</dt>
</dl>
</td>
<td width="60%">
Indicates that the callback wants
content in any format.

</td>
</tr>
</table>

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbacks2">IDebugOutputCallbacks2</a>
