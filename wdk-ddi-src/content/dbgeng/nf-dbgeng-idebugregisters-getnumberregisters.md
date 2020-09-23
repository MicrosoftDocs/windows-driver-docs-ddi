---
UID: NF:dbgeng.IDebugRegisters.GetNumberRegisters
title: IDebugRegisters::GetNumberRegisters (dbgeng.h)
description: The GetNumberRegisters method returns the number of registers on the target computer.
old-location: debugger\getnumberregisters.htm
tech.root: debugger
ms.assetid: 51c521fc-e89c-49c9-8110-de31af3bed83
ms.date: 05/03/2018
keywords: ["IDebugRegisters::GetNumberRegisters"]
ms.keywords: GetNumberRegisters, GetNumberRegisters method [Windows Debugging], GetNumberRegisters method [Windows Debugging],IDebugRegisters interface, GetNumberRegisters method [Windows Debugging],IDebugRegisters2 interface, IDebugRegisters interface [Windows Debugging],GetNumberRegisters method, IDebugRegisters.GetNumberRegisters, IDebugRegisters2 interface [Windows Debugging],GetNumberRegisters method, IDebugRegisters2::GetNumberRegisters, IDebugRegisters::GetNumberRegisters, IDebugRegisters_b2fa1d95-0331-4c27-a3af-3cc8e895e88f.xml, dbgeng/IDebugRegisters2::GetNumberRegisters, dbgeng/IDebugRegisters::GetNumberRegisters, debugger.getnumberregisters
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
 - IDebugRegisters::GetNumberRegisters
 - dbgeng/IDebugRegisters::GetNumberRegisters
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugRegisters.GetNumberRegisters
 - IDebugRegisters2.GetNumberRegisters
---

# IDebugRegisters::GetNumberRegisters


## -description

The <b>GetNumberRegisters</b> method returns the number of <a href="/windows-hardware/drivers/debugger/registers">registers</a> on the target computer.

## -parameters

### -param Number 

[out]
Receives the number of registers on the target's computer.

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

For an overview of the <a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a> interface and other register-related methods, see <a href="/windows-hardware/drivers/debugger/registers">Registers</a>.