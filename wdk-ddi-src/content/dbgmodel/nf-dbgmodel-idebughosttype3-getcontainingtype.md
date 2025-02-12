---
UID: NF:dbgmodel.IDebugHostType3.GetContainingType
tech.root: debugger
title: IDebugHostType3::GetContainingType
ms.date: 01/26/2025
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
 - IDebugHostType3::GetContainingType
f1_keywords:
 - IDebugHostType3::GetContainingType
 - dbgmodel/IDebugHostType3::GetContainingType
dev_langs:
 - c++
helpviewer_keywords:
 - GetContainingType
---

## -description

The GetContainingType method returns the type of the containing parent (the type that contains this symbol).

## -parameters

### -param containingParentType

A pointer to a pointer variable that receives the IDebugHostType3 interface of the containing parent's type.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)