---
UID: NC:dbgeng.PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES
title: PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES
author: windows-driver-content
description: The FreeStackSymFrames callback function frees memory from a stack provider.
old-location: debugger\freestacksymframes.htm
old-project: debugger
ms.assetid: E66742D4-A972-4096-8DDC-E8F42E8B8D25
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.freestacksymframes, FreeStackSymFrames, FreeStackSymFrames callback function [Windows Debugging], FreeStackSymFrames, PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES, PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES, dbgeng/FreeStackSymFrames
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
-	FreeStackSymFrames
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES callback


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

## -prototype


````
 CALLBACK* PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES FreeStackSymFrames;
````


## -parameters




### -param StackSymFrames [in, optional]

A stack to free.


## -returns


If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



## -remarks


After <i>FreeStackSymFrames</i> is called, the debugger calls the stack provider to free memory.

<i>FreeStackSymFrames</i> is called <b>PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES</b>   in the Dbgeng.h header file.



## -see-also

<a href="..\dbgeng\nc-dbgeng-pdebug_stack_provider_endthreadstackreconstruction.md">EndThreadStackReconstruction</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES callback function%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

