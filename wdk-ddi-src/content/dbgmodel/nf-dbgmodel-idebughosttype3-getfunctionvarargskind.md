---
UID: NF:dbgmodel.IDebugHostType3.GetFunctionVarArgsKind
tech.root: debugger
title: IDebugHostType3::GetFunctionVarArgsKind
ms.date: 01/26/2025
targetos: Windows
description: The GetFunctionVarArgsKind method returns whether a given function utilizes a variable argument list, and if so, what style of variable arguments it utilizes.
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
 - IDebugHostType3::GetFunctionVarArgsKind
f1_keywords:
 - IDebugHostType3::GetFunctionVarArgsKind
 - dbgmodel/IDebugHostType3::GetFunctionVarArgsKind
dev_langs:
 - c++
helpviewer_keywords:
 - GetFunctionVarArgsKind
---

## -description

The GetFunctionVarArgsKind method returns whether a given function utilizes a variable argument list, and if so, what style of variable arguments it utilizes. Such is defined by a member of the [VarArgsKind enumeration](ne-dbgmodel-varargskind.md) defined as follows:

|Enumerant |	Meaning|
|---------|---------|
|VarArgsNone |	The function does not take any variable arguments.|
|VarArgsCStyle |	The function is a C-style varargs function (returnType(arg1, arg2, ...)). The number of arguments reported by the function does not include the ellipsis argument. Any variable argument passing occurs after the number of arguments returned by the [GetFunctionParameterTypeCount method](nf-dbgmodel-idebughosttype3-getfunctionparametertypecount.md).|

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

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)
