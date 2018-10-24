---
UID: NF:dbgeng.IDebugSymbols.GetSymbolPath
title: IDebugSymbols::GetSymbolPath
author: windows-driver-content
description: The GetSymbolPath method returns the symbol path.
old-location: debugger\getsymbolpath.htm
tech.root: debugger
ms.assetid: bee6d7c5-b866-4b48-859e-9acb2219e7c1
ms.date: 05/03/2018
ms.keywords: GetSymbolPath, GetSymbolPath method [Windows Debugging], GetSymbolPath method [Windows Debugging],IDebugSymbols interface, GetSymbolPath method [Windows Debugging],IDebugSymbols2 interface, GetSymbolPath method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],GetSymbolPath method, IDebugSymbols.GetSymbolPath, IDebugSymbols2 interface [Windows Debugging],GetSymbolPath method, IDebugSymbols2::GetSymbolPath, IDebugSymbols3 interface [Windows Debugging],GetSymbolPath method, IDebugSymbols3::GetSymbolPath, IDebugSymbols::GetSymbolPath, IDebugSymbols_b13afb68-0f30-477d-be1b-a2b49ae40081.xml, dbgeng/IDebugSymbols2::GetSymbolPath, dbgeng/IDebugSymbols3::GetSymbolPath, dbgeng/IDebugSymbols::GetSymbolPath, debugger.getsymbolpath
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
-	IDebugSymbols.GetSymbolPath
-	IDebugSymbols2.GetSymbolPath
-	IDebugSymbols3.GetSymbolPath
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols::GetSymbolPath


## -description


The <b>GetSymbolPath</b>  method returns the symbol path.


## -parameters




### -param Buffer [out, optional]

Receives the symbol path.  This is a string that contains symbol path elements separated by semicolons (<b>;</b>).  Each symbol path element can specify either a directory or a symbol server.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.


### -param PathSize [out, optional]

Receives the size, in characters, of the symbol path.


## -returns



These methods can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful. However, the buffer was not large enough to hold the symbol path and the path was truncated.

</td>
</tr>
</table>
 




## -remarks



For more information about manipulating the symbol path, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560150">Using Symbols</a>.  For an overview of the symbol path and its syntax, see <a href="https://msdn.microsoft.com/705df98f-717f-40ad-a424-101826970691">Symbol Path</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538110">AppendSymbolPath</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550856">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550864">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556802">SetSymbolPath</a>
 

 

