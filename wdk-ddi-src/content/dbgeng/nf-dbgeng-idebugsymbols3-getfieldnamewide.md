---
UID: NF:dbgeng.IDebugSymbols3.GetFieldNameWide
title: IDebugSymbols3::GetFieldNameWide (dbgeng.h)
description: The GetFieldNameWide method returns the name of a field within a structure.
old-location: debugger\getfieldnamewide.htm
tech.root: debugger
ms.assetid: e27c6af5-c9fa-4fe6-ad39-82ea59a0f27b
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetFieldNameWide"]
ms.keywords: GetFieldNameWide, GetFieldNameWide method [Windows Debugging], GetFieldNameWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetFieldNameWide method, IDebugSymbols3.GetFieldNameWide, IDebugSymbols3::GetFieldNameWide, dbgeng/IDebugSymbols3::GetFieldNameWide, debugger.getfieldnamewide
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
 - IDebugSymbols3::GetFieldNameWide
 - dbgeng/IDebugSymbols3::GetFieldNameWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols3.GetFieldNameWide
---

# IDebugSymbols3::GetFieldNameWide


## -description

The <b>GetFieldNameWide</b>  method returns the name of a field within a structure.

## -parameters

### -param Module 

[in]
Specifies the base address of the module in which the structure was defined.

### -param TypeId 

[in]
Specifies the type ID of the structure.

### -param FieldIndex 

[in]
Specifies the index of the desired field within the structure.

### -param NameBuffer 

[out, optional]
Receives the field's name.  If <i>NameBuffer</i> is <b>NULL</b>, this information is not returned.

### -param NameBufferSize 

[in]
Specifies the size in characters of the buffer <i>NameBuffer</i>.

### -param NameSize 

[out, optional]
Receives the size in characters of the field's name.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.

## -returns

This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
The method was successful. However, <i>NameBuffer</i> was not large enough to hold the field's name and it was truncated.

</td>
</tr>
</table>

## -remarks

For more information about symbols, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/symbols4">Symbols</a>.

