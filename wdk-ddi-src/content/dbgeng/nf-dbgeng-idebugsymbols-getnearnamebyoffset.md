---
UID: NF:dbgeng.IDebugSymbols.GetNearNameByOffset
title: IDebugSymbols::GetNearNameByOffset method
author: windows-driver-content
description: The GetNearNameByOffset method returns the name of a symbol that is located near the specified location.
old-location: debugger\getnearnamebyoffset.htm
old-project: debugger
ms.assetid: bcda26ae-484e-41b9-b86a-552b5cecb9a7
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetNearNameByOffset method [Windows Debugging], GetNearNameByOffset method [Windows Debugging], IDebugSymbols interface, GetNearNameByOffset method [Windows Debugging], IDebugSymbols2 interface, GetNearNameByOffset method [Windows Debugging], IDebugSymbols3 interface, GetNearNameByOffset,IDebugSymbols.GetNearNameByOffset, IDebugSymbols, IDebugSymbols interface [Windows Debugging], GetNearNameByOffset method, IDebugSymbols2 interface [Windows Debugging], GetNearNameByOffset method, IDebugSymbols2::GetNearNameByOffset, IDebugSymbols3 interface [Windows Debugging], GetNearNameByOffset method, IDebugSymbols3::GetNearNameByOffset, IDebugSymbols::GetNearNameByOffset, IDebugSymbols_cdd9bec8-6fe8-4523-ac98-df3ce90fd073.xml, dbgeng/IDebugSymbols2::GetNearNameByOffset, dbgeng/IDebugSymbols3::GetNearNameByOffset, dbgeng/IDebugSymbols::GetNearNameByOffset, debugger.getnearnamebyoffset
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
-	dbgeng.h
apiname:
-	IDebugSymbols.GetNearNameByOffset
-	IDebugSymbols2.GetNearNameByOffset
-	IDebugSymbols3.GetNearNameByOffset
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols::GetNearNameByOffset method


## -description


The <b>GetNearNameByOffset</b>  method returns the name of a symbol that is located near the specified location.


## -syntax


````
HRESULT GetNearNameByOffset(
  [in]            ULONG64  Offset,
  [in]            LONG     Delta,
  [out, optional] PSTR     NameBuffer,
  [in]            ULONG    NameBufferSize,
  [out, optional] PULONG   NameSize,
  [out, optional] PULONG64 Displacement
);
````


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

<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547183">GetNameByOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548035">GetOffsetByName</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::GetNearNameByOffset method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

