---
UID: NN:dbgeng.IDebugPlmClient2
title: IDebugPlmClient2
author: windows-driver-content
description: This interface supports Process Lifecycle Management (PLM) for the debug client.
old-location: debugger\idebugplmclient2.htm
old-project: debugger
ms.assetid: 22AACAD1-292B-42D9-95F7-A3654E2077FB
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugPlmClient2, IDebugPlmClient2 interface [Windows Debugging], IDebugPlmClient2 interface [Windows Debugging], described, dbgeng/IDebugPlmClient2, debugger.idebugplmclient2
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
-	IDebugPlmClient2
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugPlmClient2 interface


## -description


This interface supports Process Lifecycle Management (PLM) for the debug client.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugPlmClient2</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IDebugPlmClient2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugPlmClient2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/47793815-F7AC-4E0D-809C-DBB7497BDA30">LaunchPlmBgTaskForDebugWide</a>
</td>
<td align="left" width="63%">
Launches a suspended Process Lifecycle Management (PLM) background task.

</td>
</tr>
</table> 

