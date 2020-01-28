---
UID: NF:dbgeng.IDebugSymbols2.GetFieldOffset
title: IDebugSymbols2::GetFieldOffset (dbgeng.h)
description: The GetFieldOffset method returns the offset of a field from the base address of an instance of a type.
old-location: debugger\getfieldoffset2.htm
tech.root: debugger
ms.assetid: 4081ddf9-673d-4df6-8698-726a70d32c03
ms.date: 05/03/2018
ms.keywords: GetFieldOffset, GetFieldOffset method [Windows Debugging], GetFieldOffset method [Windows Debugging],IDebugSymbols interface, GetFieldOffset method [Windows Debugging],IDebugSymbols2 interface, GetFieldOffset method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],GetFieldOffset method, IDebugSymbols2 interface [Windows Debugging],GetFieldOffset method, IDebugSymbols2.GetFieldOffset, IDebugSymbols2::GetFieldOffset, IDebugSymbols3 interface [Windows Debugging],GetFieldOffset method, IDebugSymbols3::GetFieldOffset, IDebugSymbols::GetFieldOffset, IDebugSymbols_3e5be57a-3af9-4fe3-a7cc-4f31fb9b54f0.xml, dbgeng/IDebugSymbols2::GetFieldOffset, dbgeng/IDebugSymbols3::GetFieldOffset, dbgeng/IDebugSymbols::GetFieldOffset, debugger.getfieldoffset2
f1_keywords:
 - "dbgeng/IDebugSymbols.GetFieldOffset"
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
- IDebugSymbols.GetFieldOffset
- IDebugSymbols2.GetFieldOffset
- IDebugSymbols3.GetFieldOffset
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols2::GetFieldOffset


## -description


The <b>GetFieldOffset</b>  method returns the offset of a field from the base address of an instance of a type.


## -parameters




### -param Module [in]

Specifies the module containing the types of both the container and the field.


### -param TypeId [in]

Specifies the type ID of the type containing the field.


### -param Field [in]

Specifies the name of the field whose offset is requested.  Subfields may be specified by using a dot-separated path.


### -param Offset [out]

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



