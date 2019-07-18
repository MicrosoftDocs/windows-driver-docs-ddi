---
UID: NN:dbgeng.IDebugClient6
title: IDebugClient6 (dbgeng.h)
description: This interface supports event context callbacks.
old-location: debugger\idebugclient6.htm
tech.root: debugger
ms.assetid: 9F8DFF33-DE07-4061-9A9E-3C8172F75EB5
ms.date: 05/03/2018
ms.keywords: IDebugClient6, IDebugClient6 interface [Windows Debugging], IDebugClient6 interface [Windows Debugging],described, dbgeng/IDebugClient6, debugger.idebugclient6
ms.topic: interface
f1_keywords:
 - "dbgeng/IDebugClient6"
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
- IDebugClient6
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient6 interface


## -description


This interface supports event context callbacks.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugClient6</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IDebugClient6</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugClient6</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient6-seteventcontextcallbacks">SetEventContextCallbacks</a>
</td>
<td align="left" width="63%">
Registers an event callbacks object with this client. 

</td>
</tr>
</table> 

