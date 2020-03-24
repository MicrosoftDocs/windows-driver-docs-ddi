---
UID: NC:dbgeng.PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES
title: PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES (dbgeng.h)
description: The FreeStackSymFrames callback function frees memory from a stack provider.
old-location: debugger\freestacksymframes.htm
tech.root: debugger
ms.assetid: E66742D4-A972-4096-8DDC-E8F42E8B8D25
ms.date: 05/03/2018
keywords: ["PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES callback function"]
ms.keywords: FreeStackSymFrames, FreeStackSymFrames callback function [Windows Debugging], PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES, PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES callback, dbgeng/FreeStackSymFrames, debugger.freestacksymframes
f1_keywords:
 - "dbgeng/FreeStackSymFrames"
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
- UserDefined
api_location:
- Dbgeng.h
api_name:
- FreeStackSymFrames
product:
- Windows
targetos: Windows
req.typenames: 
---

# PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES callback function


## -description


The <i>FreeStackSymFrames</i> callback function frees memory from a stack provider.
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre> CALLBACK* PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES FreeStackSymFrames;</pre>
</td>
</tr>
</table></span></div>

## -parameters




### -param StackSymFrames [in, optional]

A stack to free.


## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



After <i>FreeStackSymFrames</i> is called, the debugger calls the stack provider to free memory.

<i>FreeStackSymFrames</i> is called <b>PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES</b>   in the Dbgeng.h header file.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nc-dbgeng-pdebug_stack_provider_endthreadstackreconstruction">EndThreadStackReconstruction</a>
 

 

