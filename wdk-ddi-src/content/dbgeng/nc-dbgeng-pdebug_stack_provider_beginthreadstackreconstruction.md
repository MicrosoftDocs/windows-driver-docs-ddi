---
UID: NC:dbgeng.PDEBUG_STACK_PROVIDER_BEGINTHREADSTACKRECONSTRUCTION
title: PDEBUG_STACK_PROVIDER_BEGINTHREADSTACKRECONSTRUCTION (dbgeng.h)
description: The BeginThreadStackReconstruction callback function causes debugger to pass the stream to the dump stack provider prior to thread enumeration.
old-location: debugger\beginthreadstackreconstruction.htm
tech.root: debugger
ms.assetid: 50CBBBED-EF1B-485F-90D3-0056AF8984E7
ms.date: 05/03/2018
ms.keywords: BeginThreadStackReconstruction, BeginThreadStackReconstruction callback function [Windows Debugging], PDEBUG_STACK_PROVIDER_BEGINTHREADSTACKRECONSTRUCTION, PDEBUG_STACK_PROVIDER_BEGINTHREADSTACKRECONSTRUCTION callback, dbgeng/BeginThreadStackReconstruction, debugger.beginthreadstackreconstruction
f1_keywords:
 - "dbgeng/BeginThreadStackReconstruction"
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
- BeginThreadStackReconstruction
product:
- Windows
targetos: Windows
req.typenames: 
---

# PDEBUG_STACK_PROVIDER_BEGINTHREADSTACKRECONSTRUCTION callback function


## -description


The <i>BeginThreadStackReconstruction</i> callback function causes debugger to pass the stream to the dump stack provider prior to thread enumeration.
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>CALLBACK* PDEBUG_STACK_PROVIDER_BEGINTHREADSTACKRECONSTRUCTION BeginThreadStackReconstruction; </pre>
</td>
</tr>
</table></span></div>

## -parameters




### -param StreamType [in]

A stream type.


### -param MiniDumpStreamBuffer [in]

A mini-dump stream buffer.


### -param BufferSize [in]

The size of the buffer.


## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



<i>BeginThreadStackReconstruction</i> is called <b>PDEBUG_STACK_PROVIDER_BEGINTHREADSTACKRECONSTRUCTION</b> in the Dbgeng.h header file.



