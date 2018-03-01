---
UID: NN:dbgeng.IDebugOutputStream
title: IDebugOutputStream
author: windows-driver-content
description: Supports the debug output stream.
old-location: debugger\idebugoutputstream.htm
old-project: debugger
ms.assetid: 7A9AB25B-2B8B-4E8A-9E67-79C56181E5D9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IDebugOutputStream, IDebugOutputStream interface [Windows Debugging], IDebugOutputStream interface [Windows Debugging], described, dbgeng/IDebugOutputStream, debugger.idebugoutputstream
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
req.lib: dbgeng.h
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
-	IDebugOutputStream
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugOutputStream interface


## -description


Supports the debug output stream.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugOutputStream</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IDebugOutputStream</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugOutputStream</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439706">Write</a>
</td>
<td align="left" width="63%">
Writes to the debug output stream.

</td>
</tr>
</table> 

