---
UID: NN:dbgeng.IDebugAdvanced3
title: IDebugAdvanced3
author: windows-driver-content
description: IDebugAdvanced3 interface
old-location: debugger\idebugadvanced3.htm
old-project: debugger
ms.assetid: f0226d35-f7a9-4220-be91-afb6d0debd36
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.idebugadvanced3, IDebugAdvanced3 interface [Windows Debugging], IDebugAdvanced3 interface [Windows Debugging], described, IDebugAdvanced3, dbgeng/IDebugAdvanced3
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugAdvanced3
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETENCRYPTIONBLTKEY
---

# IDebugAdvanced3 interface


## -description




## -members

The <b>IDebugAdvanced3</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545435">FindSourceFileAndTokenWide</a>
</td>
<td align="left" width="63%">
Returns the filename of a source file on the source path or return the value of a variable associated with a file token.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548327">GetSourceFileInformationWide</a>
</td>
<td align="left" width="63%">
Returns specified information about a source file.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548515">GetSymbolInformationWide</a>
</td>
<td align="left" width="63%">
Returns specified information about a symbol.

</td>
</tr>
</table>Returns the filename of a source file on the source path or return the value of a variable associated with a file token.

Returns specified information about a source file.

Returns specified information about a symbol.

 


## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugadvanced2.md">IDebugAdvanced2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugAdvanced3 interface%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

