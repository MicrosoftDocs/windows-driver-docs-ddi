---
UID: NF:dbgeng.IDebugRegisters2.GetDescription
title: IDebugRegisters2::GetDescription (dbgeng.h)
description: The GetDescription method returns the description of a register. This method belongs to the IDebugRegisters2 interface.
old-location: debugger\getdescription.htm
tech.root: debugger
ms.date: 02/06/2022
keywords: ["IDebugRegisters2::GetDescription"]
ms.keywords: GetDescription, GetDescription method [Windows Debugging], GetDescription method [Windows Debugging],IDebugRegisters interface, GetDescription method [Windows Debugging],IDebugRegisters2 interface, IDebugRegisters interface [Windows Debugging],GetDescription method, IDebugRegisters2 interface [Windows Debugging],GetDescription method, IDebugRegisters2.GetDescription, IDebugRegisters2::GetDescription, IDebugRegisters::GetDescription, IDebugRegisters_aa062ab9-e090-4cad-b875-b6e99a019c16.xml, dbgeng/IDebugRegisters2::GetDescription, dbgeng/IDebugRegisters::GetDescription, debugger.getdescription
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
 - IDebugRegisters2::GetDescription
 - dbgeng/IDebugRegisters2::GetDescription
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugRegisters2::GetDescription
---

# IDebugRegisters2::GetDescription


## -description

The <b>GetDescription</b>  method returns the description of a register.

## -parameters

### -param Register [in]


Specifies the index of the register for which the description is requested.

### -param NameBuffer [out, optional]


Specifies the buffer in which to store the name of the register.  If <i>NameBuffer</i> is <b>NULL</b>, this information is not returned.

### -param NameBufferSize [in]


Specifies the size, in characters, of the buffer that  <i>NameBuffer</i> specifies. This size includes the space for the '\0' terminating character.

### -param NameSize [out, optional]


Receives the size, in characters, of the register's name in <i>NameBuffer</i> buffer. This size includes the space for the '\0' terminating character. If <i>NameSize</i> is <b>NULL</b>, this information is not returned.

### -param Desc [out, optional]


Receives the description of the register.  See <a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_register_description">DEBUG_REGISTER_DESCRIPTION</a> for more details.

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
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful. However, the buffer was not large enough to hold the register's name, so it was truncated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_UNEXPECTED</b></dt>
</dl>
</td>
<td width="60%">
No target machine has been specified, or a description of the register could not be found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The index of the register requested is greater than the total number of registers on the target's machine.

</td>
</tr>
</table>

## -remarks

For an overview of the <a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a> interface and other register-related methods, see <a href="/windows-hardware/drivers/debugger/registers">Registers</a>.

