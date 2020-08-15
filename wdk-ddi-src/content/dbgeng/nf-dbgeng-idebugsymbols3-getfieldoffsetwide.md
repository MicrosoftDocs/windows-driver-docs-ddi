---
UID: NF:dbgeng.IDebugSymbols3.GetFieldOffsetWide
title: IDebugSymbols3::GetFieldOffsetWide (dbgeng.h)
description: The GetFieldOffsetWide method returns the offset of a field from the base address of an instance of a type.
old-location: debugger\getfieldoffsetwide.htm
tech.root: debugger
ms.assetid: 4a9b90dd-72b2-4625-8b73-bc0dca6ba905
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetFieldOffsetWide"]
ms.keywords: GetFieldOffsetWide, GetFieldOffsetWide method [Windows Debugging], GetFieldOffsetWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetFieldOffsetWide method, IDebugSymbols3.GetFieldOffsetWide, IDebugSymbols3::GetFieldOffsetWide, dbgeng/IDebugSymbols3::GetFieldOffsetWide, debugger.getfieldoffsetwide
f1_keywords:
 - "dbgeng/IDebugSymbols3.GetFieldOffsetWide"
 - "IDebugSymbols3.GetFieldOffsetWide"
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
- IDebugSymbols3.GetFieldOffsetWide
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetFieldOffsetWide


## -description


The <b>GetFieldOffsetWide</b>  method returns the offset of a field from the base address of an instance of a type.


## -parameters




### -param Module 
[in]
Specifies the module containing the types of both the container and the field.


### -param TypeId 
[in]
Specifies the type ID of the type containing the field.


### -param Field 
[in]
Specifies the name of the field whose offset is requested.  Subfields may be specified by using a dot-separated path.


### -param Offset 
[out]
Receives the offset of the specified field from the base memory location of an instance of the type. 


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
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The field <i>Field</i> could not be found in the type specified by <i>TypeId</i>.

</td>
</tr>
</table>
 




## -remarks



An example of a dot-separated path for the <i>Field</i> parameter is as follows.  Suppose the MyStruct structure contains a field <b>MyField</b> of type MySubStruct, and the MySubStruct structure contains the field <b>MySubField</b>.  Then the location of this field relative to the location of MyStruct structure can be found by setting the <i>Field</i> parameter to "MyField.MySubField".

For more information about types, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/types">Types</a>.



