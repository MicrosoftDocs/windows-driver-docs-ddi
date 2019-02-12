---
UID: NF:dbgmodel.IDebugHostType2.GetFunctionVarArgsKind
title: IDebugHostType2::GetFunctionVarArgsKind (dbgmodel.h)
description: The GetFunctionVarArgsKind method returns whether a given function utilizes a variable argument list, and if so, what style of variable arguments it utilizes. 
ms.assetid: 321e50d4-8359-43e3-a593-18c2bb2cac87
ms.date: 08/22/2018
ms.topic: method
ms.keywords: IDebugHostType2::GetFunctionVarArgsKind, GetFunctionVarArgsKind, IDebugHostType2.GetFunctionVarArgsKind, IDebugHostType2::GetFunctionVarArgsKind, IDebugHostType2.GetFunctionVarArgsKind
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDebugHostType2.GetFunctionVarArgsKind
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostType2::GetFunctionVarArgsKind


## -description

The GetFunctionVarArgsKind method returns whether a given function utilizes a variable argument list, and if so, what style of variable arguments it utilizes. Such is defined by a member of the VarArgsKind enumeration defined as follows:

Enumerant |	Meaning
|---------|---------|
VarArgsNone |	The function does not take any variable arguments.
VarArgsCStyle |	The function is a C-style varargs function (returnType(arg1, arg2, ...)). The number of arguments reported by the function does not include the ellipsis argument. Any variable argument passing occurs after the number of arguments returned by the GetFunctionParameterTypeCount method.



## -parameters

### -param varArgsKind
A value of the VarArgsKind enumeration indicating whether the function is a varargs function and, if so, what style of variable arguments it utilizes.


## -returns
This method returns HRESULT that indicates success or failure. This method will not fail on a non varargs function.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostType> spType; /* get a type for a function (see FindTypeByName) */

ComPtr<IDebugHostType2> spType2;
if (SUCCEEDED(spType.As(&spType2)))
{
    VarArgsKind vaKind;
    if (SUCCEEDED(spType->GetFunctionVarArgsKind(&vaKind)))
    {
        // vaKind indicates whether the function is varargs and, if so, what 
        // style of varargs the function utilizes.
    }
}
```

## -see-also

[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)
