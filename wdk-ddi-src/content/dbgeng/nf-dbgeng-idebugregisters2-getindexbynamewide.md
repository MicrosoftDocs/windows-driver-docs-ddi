---
UID: NF:dbgeng.IDebugRegisters2.GetIndexByNameWide
title: IDebugRegisters2::GetIndexByNameWide (dbgeng.h)
description: The GetIndexByNameWide method returns the index of the named register.
old-location: debugger\getindexbynamewide.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugRegisters2::GetIndexByNameWide"]
ms.keywords: GetIndexByNameWide, GetIndexByNameWide method [Windows Debugging], GetIndexByNameWide method [Windows Debugging],IDebugRegisters2 interface, IDebugRegisters2 interface [Windows Debugging],GetIndexByNameWide method, IDebugRegisters2.GetIndexByNameWide, IDebugRegisters2::GetIndexByNameWide, dbgeng/IDebugRegisters2::GetIndexByNameWide, debugger.getindexbynamewide
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
 - IDebugRegisters2::GetIndexByNameWide
 - dbgeng/IDebugRegisters2::GetIndexByNameWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugRegisters2.GetIndexByNameWide
---

# IDebugRegisters2::GetIndexByNameWide


## -description

The <b>GetIndexByNameWide</b> method returns the index of the named register.

## -parameters

### -param Name 

[in]
Specifies the name of the register whose index is requested.

### -param Index 

[out]
Receives the index of the register.

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
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The register was not found.

</td>
</tr>
</table>

## -remarks

For an overview of the <a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a> interface and other register-related methods, see <a href="/windows-hardware/drivers/debugger/registers">Registers</a>.
