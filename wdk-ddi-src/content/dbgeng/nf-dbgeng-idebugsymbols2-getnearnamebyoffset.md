---
UID: NF:dbgeng.IDebugSymbols2.GetNearNameByOffset
title: IDebugSymbols2::GetNearNameByOffset
description: The GetNearNameByOffset method returns the name of a symbol that is located near the specified location.
old-location: debugger\getnearnamebyoffset.htm
tech.root: debugger
ms.assetid: bcda26ae-484e-41b9-b86a-552b5cecb9a7
ms.date: 05/03/2018
ms.keywords: GetNearNameByOffset, GetNearNameByOffset method [Windows Debugging], GetNearNameByOffset method [Windows Debugging],IDebugSymbols interface, GetNearNameByOffset method [Windows Debugging],IDebugSymbols2 interface, GetNearNameByOffset method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],GetNearNameByOffset method, IDebugSymbols2 interface [Windows Debugging],GetNearNameByOffset method, IDebugSymbols2.GetNearNameByOffset, IDebugSymbols2::GetNearNameByOffset, IDebugSymbols3 interface [Windows Debugging],GetNearNameByOffset method, IDebugSymbols3::GetNearNameByOffset, IDebugSymbols::GetNearNameByOffset, IDebugSymbols_cdd9bec8-6fe8-4523-ac98-df3ce90fd073.xml, dbgeng/IDebugSymbols2::GetNearNameByOffset, dbgeng/IDebugSymbols3::GetNearNameByOffset, dbgeng/IDebugSymbols::GetNearNameByOffset, debugger.getnearnamebyoffset
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
-	IDebugSymbols.GetNearNameByOffset
-	IDebugSymbols2.GetNearNameByOffset
-	IDebugSymbols3.GetNearNameByOffset
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols2::GetNearNameByOffset


## -description


The <b>GetNearNameByOffset</b>  method returns the name of a symbol that is located near the specified location.


## -parameters




### -param Offset [in]

Specifies the location in the target's virtual address space of the symbol from which the desired symbol is determined.


### -param Delta [in]

Specifies the relationship between the desired symbol and the symbol located at <i>Offset</i>.  If positive, the engine will return the symbol that is <i>Delta</i> symbols after the symbol located at <i>Offset</i>.  If negative, the engine will return the symbol that is <i>Delta</i> symbols before the symbol located at <i>Offset</i>.


### -param NameBuffer [out, optional]

Receives the symbol's name.  The name is qualified by the module to which the symbol belongs (for example, <b>mymodule!main</b>).  If <i>NameBuffer</i> is <b>NULL</b>, this information is not returned.


### -param NameBufferSize [in]

Specifies the size in characters of the buffer <i>NameBuffer</i>.


### -param NameSize [out, optional]

Receives the size in characters of the symbol's name.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.


### -param Displacement [out, optional]

Receives the difference between the value of <i>Offset</i> and the location in the target's memory address space of the symbol.  If <i>Displacement</i> is <b>NULL</b>, this information is not returned.


## -returns



This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
The method was successful.  However, the buffer was not large enough to hold the symbol's name so it was truncated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
No symbol matching the specifications of <i>Offset</i> and <i>Delta</i> was found.

</td>
</tr>
</table>
 




## -remarks



By increasing or decreasing the value of <i>Delta</i>, these methods can be used to iterate over the target's symbols starting at a particular location.

If <i>Delta</i> is zero, these methods behave the same way as <a href="https://msdn.microsoft.com/library/windows/hardware/ff547183">GetNameByOffset</a>.

For more information about symbols and symbol names, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547183">GetNameByOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548035">GetOffsetByName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550856">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550864">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

