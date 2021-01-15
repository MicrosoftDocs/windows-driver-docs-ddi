---
UID: NF:dbgeng.IDebugRegisters2.GetNumberPseudoRegisters
title: IDebugRegisters2::GetNumberPseudoRegisters (dbgeng.h)
description: The GetNumberPseudoRegisters method returns the number of pseudo-registers that are maintained by the debugger engine.
old-location: debugger\getnumberpseudoregisters.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugRegisters2::GetNumberPseudoRegisters"]
ms.keywords: GetNumberPseudoRegisters, GetNumberPseudoRegisters method [Windows Debugging], GetNumberPseudoRegisters method [Windows Debugging],IDebugRegisters2 interface, IDebugRegisters2 interface [Windows Debugging],GetNumberPseudoRegisters method, IDebugRegisters2.GetNumberPseudoRegisters, IDebugRegisters2::GetNumberPseudoRegisters, IDebugRegisters_e12950ac-f9b2-4ed2-9ce1-bc3088b65ef1.xml, dbgeng/IDebugRegisters2::GetNumberPseudoRegisters, debugger.getnumberpseudoregisters
req.header: dbgeng.h
req.include-header: DbgEng.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugRegisters2::GetNumberPseudoRegisters
 - dbgeng/IDebugRegisters2::GetNumberPseudoRegisters
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugRegisters2::GetNumberPseudoRegisters
---

# IDebugRegisters2::GetNumberPseudoRegisters


## -description

The <b>GetNumberPseudoRegisters</b> method returns the number of pseudo-registers that are maintained by the debugger engine.

## -parameters

### -param Number 

[out]
Receives the number of pseudo-registers that are maintained by the debugger engine.

## -returns

This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="/windows-hardware/drivers/debugger/hresult-values">HRESULT Values</a>.

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

## -remarks

Not all of the pseudo-registers are available in all debugging sessions or at all times in a particular session.

The valid indices for pseudo-registers are between zero and the number of pseudo-registers, minus one.

For an overview of the <a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a> interface and other register-related methods, see <a href="/windows-hardware/drivers/debugger/registers">Registers</a>.

