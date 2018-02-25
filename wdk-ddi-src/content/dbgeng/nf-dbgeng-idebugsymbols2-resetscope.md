---
UID: NF:dbgeng.IDebugSymbols2.ResetScope
title: IDebugSymbols2::ResetScope method
author: windows-driver-content
description: The ResetScope method resets the current scope to the default scope of the current thread.
old-location: debugger\resetscope.htm
old-project: debugger
ms.assetid: de8b7c44-98a6-457d-8c04-05d4fc76be16
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., 2, :, D, I, IDebugSymbols, IDebugSymbols interface [Windows Debugging], ResetScope method, IDebugSymbols2, IDebugSymbols2 interface [Windows Debugging], ResetScope method, IDebugSymbols2::ResetScope, IDebugSymbols3 interface [Windows Debugging], ResetScope method, IDebugSymbols3::ResetScope, IDebugSymbols::ResetScope, IDebugSymbols_e3d0b307-57e7-4bc1-83f6-3352dd33a7aa.xml, R, ResetScope method [Windows Debugging], ResetScope method [Windows Debugging], IDebugSymbols interface, ResetScope method [Windows Debugging], IDebugSymbols2 interface, ResetScope method [Windows Debugging], IDebugSymbols3 interface, ResetScope,IDebugSymbols.ResetScope, ResetScope,IDebugSymbols2.ResetScope, S, b, c, dbgeng/IDebugSymbols2::ResetScope, dbgeng/IDebugSymbols3::ResetScope, dbgeng/IDebugSymbols::ResetScope, debugger.resetscope, e, g, l, m, o, p, s, t, u, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Dbgeng.h
apiname:
-	IDebugSymbols.ResetScope
-	IDebugSymbols2.ResetScope
-	IDebugSymbols3.ResetScope
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols2::ResetScope method


## -description


The <b>ResetScope</b> method resets the current scope to the default scope of the current thread.


## -syntax


````
HRESULT ResetScope();
````


## -parameters






## -returns



<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



For more information about scopes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556773">SetScope</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548270">GetScope</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::ResetScope method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

