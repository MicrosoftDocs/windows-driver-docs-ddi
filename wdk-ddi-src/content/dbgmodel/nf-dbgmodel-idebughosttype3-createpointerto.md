---
UID: NF:dbgmodel.IDebugHostType3.CreatePointerTo
tech.root: debugger
title: IDebugHostType3::CreatePointerTo
ms.date: 01/29/2025
targetos: Windows
description: The CreatePointerTo method, when called on a type, gets a new IDebugHostType that is a pointer to the type.
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
 - IDebugHostType3::CreatePointerTo
f1_keywords:
 - IDebugHostType3::CreatePointerTo
 - dbgmodel/IDebugHostType3::CreatePointerTo
dev_langs:
 - c++
helpviewer_keywords:
 - CreatePointerTo
---

## -description

For any given type, this returns a new [IDebugHostType3](nn-dbgmodel-idebughosttype3.md) which is a pointer to this type.
The kind of pointer is supplied by the "kind" argument.

## -parameters

### -param kind

The kind of pointer to create (e.g.: a standard pointer, a C++ reference, a C++ rvalue reference, etc…)

### -param newType

The newly created pointer type will be returned here.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)