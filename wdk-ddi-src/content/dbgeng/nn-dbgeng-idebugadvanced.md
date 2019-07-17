---
UID: NN:dbgeng.IDebugAdvanced
title: IDebugAdvanced (dbgeng.h)
description: IDebugAdvanced interface
old-location: debugger\idebugadvanced.htm
tech.root: debugger
ms.assetid: 773c93fe-1eec-4951-960e-67164dcb41ce
ms.date: 05/03/2018
ms.keywords: IDebugAdvanced, IDebugAdvanced interface [Windows Debugging], IDebugAdvanced interface [Windows Debugging],described, IDebugAdvanced_73a2f722-f225-466b-aecc-2c7e6999e25f.xml, dbgeng/IDebugAdvanced, debugger.idebugadvanced
ms.topic: interface
f1_keywords:
 - "dbgeng/IDebugAdvanced"
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
- IDebugAdvanced
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugAdvanced interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugAdvanced</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IDebugAdvanced</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugAdvanced</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugadvanced3-getthreadcontext">GetThreadContext</a>
</td>
<td align="left" width="63%">
Returns the current thread context.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugadvanced3-setthreadcontext">SetThreadContext</a>
</td>
<td align="left" width="63%">
Sets the current thread context.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugadvanced2">IDebugAdvanced2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugadvanced3">IDebugAdvanced3</a>
 

 

