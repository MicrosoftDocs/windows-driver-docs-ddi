---
UID: NF:dbgeng.IDebugOutputCallbacks2.GetInterestMask
title: IDebugOutputCallbacks2::GetInterestMask (dbgeng.h)
description: Allows the callback object to describe which kinds of output notifications it wants to receive.
old-location: debugger\idebugoutputcallbacks2_getinterestmask.htm
tech.root: debugger
ms.assetid: BA710D92-63F4-4B4B-868A-58074FC052E9
ms.date: 05/03/2018
ms.keywords: DEBUG_OUTCBI_ANY_FORMAT, DEBUG_OUTCBI_DML, DEBUG_OUTCBI_EXPLICIT_FLUSH, DEBUG_OUTCBI_TEXT, GetInterestMask, GetInterestMask method [Windows Debugging], GetInterestMask method [Windows Debugging],IDebugOutputCallbacks2 interface, IDebugOutputCallbacks2 interface [Windows Debugging],GetInterestMask method, IDebugOutputCallbacks2.GetInterestMask, IDebugOutputCallbacks2::GetInterestMask, dbgeng/IDebugOutputCallbacks2::GetInterestMask, debugger.idebugoutputcallbacks2_getinterestmask
ms.topic: method
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
- IDebugOutputCallbacks2.GetInterestMask
product:
- Windows
targetos: Windows
req.typenames: 
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



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugoutputcallbacks2">IDebugOutputCallbacks2</a>
 

 

