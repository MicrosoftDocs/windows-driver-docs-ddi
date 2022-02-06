---
UID: NF:dbgeng.IDebugSymbols3.GetConstantNameWide
title: IDebugSymbols3::GetConstantNameWide (dbgeng.h)
description: The GetConstantNameWide method returns the name of the specified constant.
old-location: debugger\getconstantnamewide.htm
tech.root: debugger
ms.date: 02/06/2022
keywords: ["IDebugSymbols3::GetConstantNameWide"]
ms.keywords: GetConstantNameWide, GetConstantNameWide method [Windows Debugging], GetConstantNameWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetConstantNameWide method, IDebugSymbols3.GetConstantNameWide, IDebugSymbols3::GetConstantNameWide, dbgeng/IDebugSymbols3::GetConstantNameWide, debugger.getconstantnamewide
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugSymbols3::GetConstantNameWide
 - dbgeng/IDebugSymbols3::GetConstantNameWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols3::GetConstantNameWide
---

# IDebugSymbols3::GetConstantNameWide


## -description

The <b>GetConstantNameWide</b>  method returns the name of the specified constant.

## -parameters

### -param Module [in]


Specifies the base address of the module in which the constant was defined.

### -param TypeId [in]


Specifies the type ID of the constant.

### -param Value [in]


Specifies the value of the constant.

### -param NameBuffer [out, optional]


Receives the constant's name.  If <i>NameBuffer</i> is <b>NULL</b>, this information is not returned.

### -param NameBufferSize [in]


Specifies the size in characters of the buffer <i>NameBuffer</i>. This size includes the space for the '\0' terminating character.

### -param NameSize [out, optional]


Receives the size in characters of the constant's name. This size includes the space for the '\0' terminating character.

## -returns

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
The method was successful. However, the buffer was not large enough for the constant's name and it was truncated.

</td>
</tr>
</table>

## -remarks

For more information about symbols, see <a href="/windows-hardware/drivers/debugger/symbols4">Symbols</a>.

