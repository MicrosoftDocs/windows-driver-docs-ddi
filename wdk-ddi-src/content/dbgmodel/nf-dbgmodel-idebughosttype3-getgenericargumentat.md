---
UID: NF:dbgmodel.IDebugHostType3.GetGenericArgumentAt
tech.root: debugger
title: IDebugHostType3::GetGenericArgumentAt
ms.date: 01/26/2025
targetos: Windows
description: The GetGenericArgumentAt method, when called on a function type, gets a generic argument at a given index in the function's argument list.
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
 - IDebugHostType3::GetGenericArgumentAt
f1_keywords:
 - IDebugHostType3::GetGenericArgumentAt
 - dbgmodel/IDebugHostType3::GetGenericArgumentAt
dev_langs:
 - c++
helpviewer_keywords:
 - GetGenericArgumentAt
---

## -description

For the "i"-th generic argument to the generic/template, this returns a new [IDebugHostSymbol](nn-dbgmodel-idebughostsymbol.md)  which represents that argument.  For templates, this is most often an [IDebugHostType](nn-dbgmodel-idebughosttype.md); however --  it may be an [IDebugHostConstant](nn-dbgmodel-idebughostconstant.md) for non-template type arguments.  

Note that it is possible for some compiler generated generics and templates that this method  will fail.

## -parameters

### -param i

The zero based index of the generic argument to returned.

### -param argument

The i’th generic argument of the type will be returned here

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)