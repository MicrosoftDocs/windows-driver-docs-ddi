---
UID: NC:dbgeng.PDEBUG_STACK_PROVIDER_ENDTHREADSTACKRECONSTRUCTION
title: PDEBUG_STACK_PROVIDER_ENDTHREADSTACKRECONSTRUCTION
author: windows-driver-content
description: The EndThreadStackReconstruction callback function may be called after stack reconstruction to clean up state.
old-location: debugger\endthreadstackreconstruction.htm
old-project: debugger
ms.assetid: 76984F28-7AC9-44FD-9D8B-CC184484C73E
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: EndThreadStackReconstruction, EndThreadStackReconstruction callback function [Windows Debugging], PDEBUG_STACK_PROVIDER_ENDTHREADSTACKRECONSTRUCTION, dbgeng/EndThreadStackReconstruction, debugger.endthreadstackreconstruction
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Dbgeng.h
apiname:
-	EndThreadStackReconstruction
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# PDEBUG_STACK_PROVIDER_ENDTHREADSTACKRECONSTRUCTION callback


## -description


The <i>EndThreadStackReconstruction</i> callback function may be called after stack reconstruction to clean up state.
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre> CALLBACK* PDEBUG_STACK_PROVIDER_ENDTHREADSTACKRECONSTRUCTION EndThreadStackReconstruction;</pre>
</td>
</tr>
</table></span></div>

## -prototype


````
 CALLBACK* PDEBUG_STACK_PROVIDER_ENDTHREADSTACKRECONSTRUCTION EndThreadStackReconstruction;
````


## -parameters




### -param void








## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



<i>EndThreadStackReconstruction</i> is called <b>PDEBUG_STACK_PROVIDER_ENDTHREADSTACKRECONSTRUCTION</b> in the Dbgeng.h header file.



