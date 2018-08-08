---
UID: NF:dbgeng.IDebugSymbolGroup2.GetSymbolOffset
title: IDebugSymbolGroup2::GetSymbolOffset
author: windows-driver-content
description: The GetSymbolOffset method retrieves the location in the process's virtual address space of a symbol in a symbol group, if the symbol has an absolute address.
old-location: debugger\getsymboloffset.htm
tech.root: debugger
ms.assetid: da3ddebc-109e-43fb-a0e9-fd89d90dbbc7
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: ComOther_11a91301-541c-4bc3-aa1e-614db8170e03.xml, GetSymbolOffset, GetSymbolOffset method [Windows Debugging], GetSymbolOffset method [Windows Debugging],IDebugSymbolGroup2 interface, IDebugSymbolGroup2 interface [Windows Debugging],GetSymbolOffset method, IDebugSymbolGroup2.GetSymbolOffset, IDebugSymbolGroup2::GetSymbolOffset, dbgeng/IDebugSymbolGroup2::GetSymbolOffset, debugger.getsymboloffset
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
-	IDebugSymbolGroup2.GetSymbolOffset
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbolGroup2::GetSymbolOffset


## -description


The <b>GetSymbolOffset</b> method retrieves the location in the process's virtual address space of a symbol in a symbol group, if the symbol has an absolute address.


## -parameters




### -param Index [in]

The index of the symbol whose address you want.  The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.


### -param Offset [out]

The location in the process's virtual address space of the symbol.


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
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The symbol does not have an absolute address.

</td>
</tr>
</table>
 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.




## -remarks



For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550846">IDebugSymbolGroup2</a>
 

 

