---
UID: NF:dbgeng.IDebugSymbols2.GetTypeId
title: IDebugSymbols2::GetTypeId (dbgeng.h)
description: The GetTypeId method looks up the specified type and return its type ID.
old-location: debugger\gettypeid.htm
tech.root: debugger
ms.assetid: 4bc82faf-a5f9-4363-8317-ad685d5b2166
ms.date: 05/03/2018
keywords: ["IDebugSymbols2::GetTypeId"]
ms.keywords: GetTypeId, GetTypeId method [Windows Debugging], GetTypeId method [Windows Debugging],IDebugSymbols interface, GetTypeId method [Windows Debugging],IDebugSymbols2 interface, GetTypeId method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],GetTypeId method, IDebugSymbols2 interface [Windows Debugging],GetTypeId method, IDebugSymbols2.GetTypeId, IDebugSymbols2::GetTypeId, IDebugSymbols3 interface [Windows Debugging],GetTypeId method, IDebugSymbols3::GetTypeId, IDebugSymbols::GetTypeId, IDebugSymbols_cf0d81fd-9bd1-4b90-a7d5-99f1cb225036.xml, dbgeng/IDebugSymbols2::GetTypeId, dbgeng/IDebugSymbols3::GetTypeId, dbgeng/IDebugSymbols::GetTypeId, debugger.gettypeid
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
 - IDebugSymbols2::GetTypeId
 - dbgeng/IDebugSymbols2::GetTypeId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols.GetTypeId
 - IDebugSymbols2.GetTypeId
 - IDebugSymbols3.GetTypeId
---

# IDebugSymbols2::GetTypeId


## -description

The <b>GetTypeId</b>  method looks up the specified type and return its type ID.

## -parameters

### -param Module 

[in]
Specifies the base address of the module to which the type belongs.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/modules">Modules</a>.  If <i>Name</i> contains a module name, <i>Module</i> is ignored.

### -param Name 

[in]
Specifies the name of the type whose type ID is desired.  If <i>Name</i> is a module-qualified name (for example <b>mymodule!main</b>), the <i>Module</i> parameter is ignored.

### -param TypeId 

[out]
Receives the type ID of the symbol.

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
</table>

## -remarks

If the specified symbol is a type, these methods return the type ID for that type; otherwise, they return the type ID for the type of the symbol.

A variable whose type was defined using <b>typedef</b> has a type ID that identifies the original type, not the type created by <b>typedef</b>.  In the following example, the type ID of <b>MyInstance</b> corresponds to the name <b>MyStruct</b> (this correspondence can be seen by passing the type ID to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-gettypename">GetTypeName</a>):


```
struct MyStruct { int a; };
typedef struct MyStruct MyType;
MyType MyInstance;
```

Moreover, calling these methods for <b>MyStruct</b> and <b>MyType</b> yields type IDs corresponding to <b>MyStruct</b> and <b>MyType</b>, respectively.

For more information about symbols and symbol names, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/symbols4">Symbols</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getoffsettypeid">GetOffsetTypeId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getsymboltypeid">GetSymbolTypeId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>

