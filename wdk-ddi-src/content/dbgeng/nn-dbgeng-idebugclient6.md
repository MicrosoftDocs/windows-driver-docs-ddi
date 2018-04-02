---
UID: NN:dbgeng.IDebugClient6
title: IDebugClient6
author: windows-driver-content
description: This interface supports event context callbacks.
old-location: debugger\idebugclient6.htm
old-project: debugger
ms.assetid: 9F8DFF33-DE07-4061-9A9E-3C8172F75EB5
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugClient6, IDebugClient6 interface [Windows Debugging], IDebugClient6 interface [Windows Debugging], described, dbgeng/IDebugClient6, debugger.idebugclient6
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
-	IDebugClient6
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient6 interface


## -description


This interface supports event context callbacks.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugClient6</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IDebugClient6</b> also has these types of members:
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
<a href="https://msdn.microsoft.com/246573DB-5FEB-4068-8DB8-950F5EDFD1A9">SetEventContextCallbacks</a>
</td>
<td align="left" width="63%">
Registers an event callbacks object with this client. 

</td>
</tr>
</table> 

