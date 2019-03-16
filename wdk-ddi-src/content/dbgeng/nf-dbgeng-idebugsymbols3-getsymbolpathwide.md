---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolPathWide
title: IDebugSymbols3::GetSymbolPathWide (dbgeng.h)
description: The GetSymbolPathWide method returns the symbol path.
old-location: debugger\getsymbolpathwide.htm
tech.root: debugger
ms.assetid: 2326130f-7e5f-492f-88a9-9eadeccc4827
ms.date: 05/03/2018
ms.keywords: GetSymbolPathWide, GetSymbolPathWide method [Windows Debugging], GetSymbolPathWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetSymbolPathWide method, IDebugSymbols3.GetSymbolPathWide, IDebugSymbols3::GetSymbolPathWide, dbgeng/IDebugSymbols3::GetSymbolPathWide, debugger.getsymbolpathwide
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugSymbols3.GetSymbolPathWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetSymbolPathWide


## -description


The <b>GetSymbolPathWide</b>  method returns the symbol path.


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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556802">SetSymbolPath</a>
 

 

