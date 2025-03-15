---
UID: NF:dbgmodel.IDebugHostFunctionIntrospection3.EnumerateInlineFunctionsByRVA
tech.root: debugger
title: IDebugHostFunctionIntrospection3::EnumerateInlineFunctionsByRVA
ms.date: 01/29/2025
targetos: Windows
description: The EnumerateInlineFunctionsByRVA method enumerates the functions that are inlined at a specific Relative Virtual Address (RVA).
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgmodel.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostFunctionIntrospection3::EnumerateInlineFunctionsByRVA
f1_keywords:
 - IDebugHostFunctionIntrospection3::EnumerateInlineFunctionsByRVA
 - dbgmodel/IDebugHostFunctionIntrospection3::EnumerateInlineFunctionsByRVA
dev_langs:
 - c++
helpviewer_keywords:
 - EnumerateInlineFunctionsByRVA
---

## -description

The EnumerateInlineFunctionsByRVA method enumerates the functions that are inlined at a specific Relative Virtual Address (RVA). The functions are enumerated from the innermost containing inline function to the outermost.

## -parameters

### -param rva

A ULONG64 value that specifies the Relative Virtual Address.

### -param inlinesEnum

A pointer to a pointer variable that receives the IDebugHostSymbolEnumerator interface of the enumerated inlined functions.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

This method is used when you need to inspect the inlined functions at a specific address in a program. It lists the functions from innermost to outermost.

**Sample Code**

```cpp
void Function1() {...};  
void Function2()  
{  
    ...  
    Function1();  // inlined  
    ...  
}  
void Function3()  
{  
    ...  
    Function2();  // inlined  
    ...  
}  
```
 
This method will enumerate Function1, followed by Function2, when called on an RVA inlined for Function1, and will enumerate only Function2 when called on an RVA inlined for Function2.

## -see-also

[IDebugHostFunctionIntrospection3 interface](nn-dbgmodel-idebughostfunctionintrospection3.md)