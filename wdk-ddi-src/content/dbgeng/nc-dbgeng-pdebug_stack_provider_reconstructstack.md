---
UID: NC:dbgeng.PDEBUG_STACK_PROVIDER_RECONSTRUCTSTACK
title: PDEBUG_STACK_PROVIDER_RECONSTRUCTSTACK (dbgeng.h)
description: The ReconstructStack callback function queries dump stream provider on a per-thread basis.
old-location: debugger\reconstructstack.htm
tech.root: debugger
ms.assetid: 639A90E8-4B2D-413B-B6F9-078C9DF1B02F
ms.date: 05/03/2018
ms.keywords: PDEBUG_STACK_PROVIDER_RECONSTRUCTSTACK, PDEBUG_STACK_PROVIDER_RECONSTRUCTSTACK callback, ReconstructStack, ReconstructStack callback function [Windows Debugging], dbgeng/ReconstructStack, debugger.reconstructstack
f1_keywords:
 - "dbgeng/ReconstructStack"
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
- ReconstructStack
product:
- Windows
targetos: Windows
req.typenames: 
---

# PDEBUG_STACK_PROVIDER_RECONSTRUCTSTACK callback function


## -description


The <i>ReconstructStack</i> callback function queries dump stream provider on a per-thread basis.
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre> CALLBACK* PDEBUG_STACK_PROVIDER_RECONSTRUCTSTACK ReconstructStack;</pre>
</td>
</tr>
</table></span></div>

## -parameters




### -param SystemThreadId [in]

A system thread ID.


### -param NativeFrames [in]

Native frames.


### -param CountNativeFrames [in]

Specifies the number of native frames.


### -param *StackSymFrames [out]

A pointer to a symbol frames stack.


### -param StackSymFramesFilled [out]

Symbol frames stack filled value.


## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



This function returns stack frames and symbolic data.

New in-line frames may be provided.

Stack dump provider must be enabled.

<i>ReconstructStack</i> is called <b>PDEBUG_STACK_PROVIDER_RECONSTRUCTSTACK</b>  in the Dbgeng.h header file.



