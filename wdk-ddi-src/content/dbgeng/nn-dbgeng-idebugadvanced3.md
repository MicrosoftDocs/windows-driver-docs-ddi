---
UID: NN:dbgeng.IDebugAdvanced3
title: IDebugAdvanced3 (dbgeng.h)
description: IDebugAdvanced3 interface
old-location: debugger\idebugadvanced3.htm
tech.root: debugger
ms.assetid: f0226d35-f7a9-4220-be91-afb6d0debd36
ms.date: 05/03/2018
ms.keywords: IDebugAdvanced3, IDebugAdvanced3 interface [Windows Debugging], IDebugAdvanced3 interface [Windows Debugging],described, dbgeng/IDebugAdvanced3, debugger.idebugadvanced3
ms.topic: interface
f1_keywords:
 - "dbgeng/IDebugAdvanced3"
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
- IDebugAdvanced3
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugAdvanced3 interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugAdvanced3</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugadvanced2">IDebugAdvanced2</a>. <b>IDebugAdvanced3</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugAdvanced3</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugadvanced3-findsourcefileandtokenwide">FindSourceFileAndTokenWide</a>
</td>
<td align="left" width="63%">
Returns the filename of a source file on the source path or return the value of a variable associated with a file token.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugadvanced3-getsourcefileinformationwide">GetSourceFileInformationWide</a>
</td>
<td align="left" width="63%">
Returns specified information about a source file.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugadvanced3-getsymbolinformationwide">GetSymbolInformationWide</a>
</td>
<td align="left" width="63%">
Returns specified information about a symbol.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugadvanced2">IDebugAdvanced2</a>
 

 

