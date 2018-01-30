---
UID: NF:dbgeng.IDebugOutputCallbacks2.GetInterestMask
title: IDebugOutputCallbacks2::GetInterestMask method
author: windows-driver-content
description: Allows the callback object to describe which kinds of output notifications it wants to receive.
old-location: debugger\idebugoutputcallbacks2_getinterestmask.htm
old-project: debugger
ms.assetid: BA710D92-63F4-4B4B-868A-58074FC052E9
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetInterestMask, DEBUG_OUTCBI_DML, DEBUG_OUTCBI_ANY_FORMAT, DEBUG_OUTCBI_EXPLICIT_FLUSH, IDebugOutputCallbacks2, IDebugOutputCallbacks2 interface [Windows Debugging], GetInterestMask method, dbgeng/IDebugOutputCallbacks2::GetInterestMask, IDebugOutputCallbacks2::GetInterestMask, debugger.idebugoutputcallbacks2_getinterestmask, DEBUG_OUTCBI_TEXT, GetInterestMask method [Windows Debugging], IDebugOutputCallbacks2 interface, GetInterestMask method [Windows Debugging]
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	IDebugOutputCallbacks2.GetInterestMask
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETENCRYPTIONBLTKEY
---

# IDebugOutputCallbacks2::GetInterestMask method


## -description


Allows the callback object to describe which kinds of output notifications it wants to receive. 


## -syntax


````
HRESULT GetInterestMask(
   PULONG Mask
);
````


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

<a href="..\dbgeng\nn-dbgeng-idebugoutputcallbacks2.md">IDebugOutputCallbacks2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugOutputCallbacks2::GetInterestMask method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

