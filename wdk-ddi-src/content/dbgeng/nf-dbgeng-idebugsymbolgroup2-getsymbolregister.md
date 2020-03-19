---
UID: NF:dbgeng.IDebugSymbolGroup2.GetSymbolRegister
title: IDebugSymbolGroup2::GetSymbolRegister (dbgeng.h)
description: The GetSymbolRegister method returns the register that contains the value or a pointer to the value of a symbol in a symbol group.
old-location: debugger\getsymbolregister.htm
tech.root: debugger
ms.assetid: 6b95ca8c-604b-4497-9798-02f362095709
ms.date: 05/03/2018
keywords: ["IDebugSymbolGroup2::GetSymbolRegister"]
ms.keywords: ComOther_9383fee9-ec27-4ccb-8768-02bd550746d7.xml, GetSymbolRegister, GetSymbolRegister method [Windows Debugging], GetSymbolRegister method [Windows Debugging],IDebugSymbolGroup2 interface, IDebugSymbolGroup2 interface [Windows Debugging],GetSymbolRegister method, IDebugSymbolGroup2.GetSymbolRegister, IDebugSymbolGroup2::GetSymbolRegister, dbgeng/IDebugSymbolGroup2::GetSymbolRegister, debugger.getsymbolregister
f1_keywords:
 - "dbgeng/IDebugSymbolGroup2.GetSymbolRegister"
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
- IDebugSymbolGroup2.GetSymbolRegister
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbolGroup2::GetSymbolRegister


## -description


The <b>GetSymbolRegister</b> method returns the register that contains the value or a pointer to the value of a symbol in a symbol group.


## -parameters




### -param Index [in]

The index of the symbol to return the register for. The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.


### -param Register [out]

The index of the register that contains the value or a pointer to the value of the symbol.


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
The symbol's value and a pointer to it are not contained in a register, or the register is not known.

</td>
</tr>
</table>
 

This method can also return error values.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.




## -remarks



For more information about symbol groups, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/scopes-and-symbol-groups">Scopes and Symbol Groups</a>.  For more information about registers and the register index, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/registers">Registers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-getnumbersymbols">GetNumberSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup2">IDebugSymbolGroup2</a>
 

 

