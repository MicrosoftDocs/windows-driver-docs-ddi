---
UID: NF:dbgmodel.IDebugHostFunctionIntrospection3.FindContainingCodeRangeByRVA
tech.root: debugger
title: IDebugHostFunctionIntrospection3::FindContainingCodeRangeByRVA
ms.date: 01/29/2025
targetos: Windows
description: The FindContainingCodeRangeByRVA method returns the sub-range of instructions that are inlined at a specific Relative Virtual Address (RVA).
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
 - IDebugHostFunctionIntrospection3::FindContainingCodeRangeByRVA
f1_keywords:
 - IDebugHostFunctionIntrospection3::FindContainingCodeRangeByRVA
 - dbgmodel/IDebugHostFunctionIntrospection3::FindContainingCodeRangeByRVA
dev_langs:
 - c++
helpviewer_keywords:
 - FindContainingCodeRangeByRVA
---

## -description

The FindContainingCodeRangeByRVA method returns the sub-range of instructions that contains a given address. For single-block functions, this will simply be the start and end of the function body. For multi-block functions, this will be the start and end of the block containing the specified Relative Virtual Address (RVA).

## -parameters

### -param rva

A ULONG64 value that specifies the Relative Virtual Address.

### -param rangeStart

A pointer to a Location structure. This parameter receives the starting location of the code range.

### -param rangeEnd

A pointer to a Location structure. This parameter receives the ending location of the code range.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostFunctionIntrospection3 interface](nn-dbgmodel-idebughostfunctionintrospection3.md)