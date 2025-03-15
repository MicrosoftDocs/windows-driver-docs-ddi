---
UID: NF:dbgmodel.IDebugHostFunctionIntrospection2.FindSourceLocationByRVA
tech.root: debugger
title: IDebugHostFunctionIntrospection2::FindSourceLocationByRVA
ms.date: 01/29/2025
targetos: Windows
description: The FindSourceLocationByRVA method retrieves the source file name and the line number for a specific Relative Virtual Address (RVA).
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
 - IDebugHostFunctionIntrospection2::FindSourceLocationByRVA
f1_keywords:
 - IDebugHostFunctionIntrospection2::FindSourceLocationByRVA
 - dbgmodel/IDebugHostFunctionIntrospection2::FindSourceLocationByRVA
dev_langs:
 - c++
helpviewer_keywords:
 - FindSourceLocationByRVA
---

## -description

The FindSourceLocationByRVA method retrieves the source file name and the line number for a specific Relative Virtual Address (RVA).

## -parameters

### -param rva

A ULONG64 value that specifies the Relative Virtual Address.

### -param sourceFile

A pointer to a BSTR variable. This parameter receives the source file name.

### -param sourceLine

A pointer to a ULONG64 variable. This parameter receives the source line number.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostFunctionIntrospection2 interface](nn-dbgmodel-idebughostfunctionintrospection2.md)