---
UID: NN:dbgeng.IDebugAdvanced2
title: IDebugAdvanced2 (dbgeng.h)
description: IDebugAdvanced2 interface
old-location: debugger\idebugadvanced2.htm
tech.root: debugger
ms.assetid: 9b5f73db-1fb8-4e07-8053-67cb5020505e
ms.date: 05/03/2018
ms.keywords: IDebugAdvanced2, IDebugAdvanced2 interface [Windows Debugging], IDebugAdvanced2 interface [Windows Debugging],described, dbgeng/IDebugAdvanced2, debugger.idebugadvanced2
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
-	IDebugAdvanced2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugAdvanced2 interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugAdvanced2</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff549798">IDebugAdvanced</a>. <b>IDebugAdvanced2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugAdvanced2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545430">FindSourceFileAndToken</a>
</td>
<td align="left" width="63%">
Returns the filename of a source file on the source path or return the value of a variable associated with a file token.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548321">GetSourceFileInformation</a>
</td>
<td align="left" width="63%">
Returns specified information about a source file.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548505">GetSymbolInformation</a>
</td>
<td align="left" width="63%">
Returns specified information about a symbol.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549226">GetSystemObjectInformation</a>
</td>
<td align="left" width="63%">
Returns information about operating system objects on the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554564">Request</a>
</td>
<td align="left" width="63%">
Performs a variety of different operations.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549798">IDebugAdvanced</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549807">IDebugAdvanced3</a>
 

 

