---
UID: NF:dbgmodel.IDebugHostField2.GetContainingType
tech.root: debugger
title: IDebugHostField2::GetContainingType
ms.date: 01/29/2025
targetos: Windows
description: The GetContainingType method returns the type of the containing parent (the type that contains this symbol).
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
 - IDebugHostField2::GetContainingType
f1_keywords:
 - IDebugHostField2::GetContainingType
 - dbgmodel/IDebugHostField2::GetContainingType
dev_langs:
 - c++
helpviewer_keywords:
 - GetContainingType
---

## -description

The GetContainingType method returns the type of the containing parent (the type that contains this symbol).

## -parameters

### -param containingParentType

A pointer to a pointer variable that receives the [IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md) of the containing parent's type.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostField2 interface](nn-dbgmodel-idebughostfield2.md)