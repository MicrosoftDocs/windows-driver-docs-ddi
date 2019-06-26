---
UID: NF:dbgeng.IDebugSymbols3.GetNameByOffsetWide
title: IDebugSymbols3::GetNameByOffsetWide (dbgeng.h)
description: The GetNameByOffsetWide method returns the name of the symbol at the specified location in the target's virtual address space.
old-location: debugger\getnamebyoffsetwide.htm
tech.root: debugger
ms.assetid: 45a041c9-029a-4fa1-91c6-562e56a30b3e
ms.date: 05/03/2018
ms.keywords: GetNameByOffsetWide, GetNameByOffsetWide method [Windows Debugging], GetNameByOffsetWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetNameByOffsetWide method, IDebugSymbols3.GetNameByOffsetWide, IDebugSymbols3::GetNameByOffsetWide, dbgeng/IDebugSymbols3::GetNameByOffsetWide, debugger.getnamebyoffsetwide
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
- IDebugSymbols3.GetNameByOffsetWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetNameByOffsetWide


## -description


The <b>GetNameByOffsetWide</b>  method returns the name of the symbol at the specified location in the target's virtual address space.


## -parameters




### -param Offset [in]

Specifies the location in the target's virtual address space of the symbol whose name is requested.  <i>Offset</i> does not need to specify the base location of the symbol; it only needs to specify a location within the symbol's memory allocation.


### -param NameBuffer [out, optional]

Receives the symbol's name.  The name is qualified by the module to which the symbol belongs (for example, <b>mymodule!main</b>).  If <i>NameBuffer</i> is <b>NULL</b>, this information is not returned.


### -param NameBufferSize [in]

Specifies the size in characters of the buffer <i>NameBuffer</i>.


### -param NameSize [out, optional]

Receives the size in characters of the symbol's name.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.


### -param Displacement [out, optional]

Receives the difference between the value of <i>Offset</i> and the base location of the symbol.  If <i>Displacement</i> is <b>NULL</b>, this information is not returned.


## -returns



This method may also return other error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
The method was successful.  However, the buffer was not large enough to hold the symbol's name, so it was truncated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
No symbol could be found at the specified location.

</td>
</tr>
</table>
 




## -remarks



For more information about symbols and symbol names, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/symbols4">Symbols</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getnearnamebyoffset">GetNearNameByOffset</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getoffsetbyname">GetOffsetByName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
 

 

