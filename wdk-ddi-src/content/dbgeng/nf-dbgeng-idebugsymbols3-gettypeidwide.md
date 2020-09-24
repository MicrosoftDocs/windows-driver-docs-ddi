---
UID: NF:dbgeng.IDebugSymbols3.GetTypeIdWide
title: IDebugSymbols3::GetTypeIdWide (dbgeng.h)
description: The GetTypeIdWide method looks up the specified type and return its type ID.
old-location: debugger\gettypeidwide.htm
tech.root: debugger
ms.assetid: 4b0f4de6-b800-4bc0-ae1d-97d877e3b91e
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetTypeIdWide"]
ms.keywords: GetTypeIdWide, GetTypeIdWide method [Windows Debugging], GetTypeIdWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetTypeIdWide method, IDebugSymbols3.GetTypeIdWide, IDebugSymbols3::GetTypeIdWide, dbgeng/IDebugSymbols3::GetTypeIdWide, debugger.gettypeidwide
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
 - IDebugSymbols3::GetTypeIdWide
 - dbgeng/IDebugSymbols3::GetTypeIdWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols3.GetTypeIdWide
---

# IDebugSymbols3::GetTypeIdWide


## -description

The <b>GetTypeIdWide</b>  method looks up the specified type and return its type ID.

## -parameters

### -param Module 

[in]
Specifies the base address of the module to which the type belongs.  For more information, see <a href="/windows-hardware/drivers/debugger/modules">Modules</a>.  If <i>Name</i> contains a module name, <i>Module</i> is ignored.

### -param Name 

[in]
Specifies the name of the type whose type ID is desired.  If <i>Name</i> is a module-qualified name (for example <b>mymodule!main</b>), the <i>Module</i> parameter is ignored.

### -param TypeId 

[out]
Receives the type ID of the symbol.

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
</table>

## -remarks

If the specified symbol is a type, these methods return the type ID for that type; otherwise, they return the type ID for the type of the symbol.

A variable whose type was defined using <b>typedef</b> has a type ID that identifies the original type, not the type created by <b>typedef</b>.  In the following example, the type ID of <b>MyInstance</b> corresponds to the name <b>MyStruct</b> (this correspondence can be seen by passing the type ID to <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-gettypename">GetTypeName</a>):


```
struct MyStruct { int a; };
typedef struct MyStruct MyType;
MyType MyInstance;
```

Moreover, calling these methods for <b>MyStruct</b> and <b>MyType</b> yields type IDs corresponding to <b>MyStruct</b> and <b>MyType</b>, respectively.

For more information about symbols and symbol names, see <a href="/windows-hardware/drivers/debugger/symbols4">Symbols</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getoffsettypeid">GetOffsetTypeId</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getsymboltypeid">GetSymbolTypeId</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>