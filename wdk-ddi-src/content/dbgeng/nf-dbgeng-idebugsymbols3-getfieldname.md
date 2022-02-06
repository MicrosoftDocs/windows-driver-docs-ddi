---
UID: NF:dbgeng.IDebugSymbols3.GetFieldName
title: IDebugSymbols3::GetFieldName (dbgeng.h)
description: The GetFieldName method returns the name of a field within a structure. This method belongs to the IDebugSymbols3 interface.
old-location: debugger\getfieldname.htm
tech.root: debugger
ms.date: 02/06/2022
keywords: ["IDebugSymbols3::GetFieldName"]
ms.keywords: GetFieldName, GetFieldName method [Windows Debugging], GetFieldName method [Windows Debugging],IDebugSymbols2 interface, GetFieldName method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols2 interface [Windows Debugging],GetFieldName method, IDebugSymbols2::GetFieldName, IDebugSymbols3 interface [Windows Debugging],GetFieldName method, IDebugSymbols3.GetFieldName, IDebugSymbols3::GetFieldName, IDebugSymbols_9956ec9a-7914-46e4-9cec-49a22a0d184f.xml, dbgeng/IDebugSymbols2::GetFieldName, dbgeng/IDebugSymbols3::GetFieldName, debugger.getfieldname
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
 - IDebugSymbols3::GetFieldName
 - dbgeng/IDebugSymbols3::GetFieldName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols3::GetFieldName
---

# IDebugSymbols3::GetFieldName


## -description

The <b>GetFieldName</b>  method returns the name of a field within a structure.

## -parameters

### -param Module [in]


Specifies the base address of the module in which the structure was defined.

### -param TypeId [in]


Specifies the type ID of the structure.

### -param FieldIndex [in]


Specifies the index of the desired field within the structure.

### -param NameBuffer [out, optional]


Receives the field's name.  If <i>NameBuffer</i> is <b>NULL</b>, this information is not returned.

### -param NameBufferSize [in]


Specifies the size in characters of the buffer <i>NameBuffer</i>. This size includes the space for the '\0' terminating character.

### -param NameSize [out, optional]


Receives the size in characters of the field's name. This size includes the space for the '\0' terminating character. If <i>NameSize</i> is <b>NULL</b>, this information is not returned.

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
The method was successful. However, <i>NameBuffer</i> was not large enough to hold the field's name and it was truncated.

</td>
</tr>
</table>

## -remarks

For more information about symbols, see <a href="/windows-hardware/drivers/debugger/symbols4">Symbols</a>.

