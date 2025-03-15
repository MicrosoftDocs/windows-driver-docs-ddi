---
UID: NF:dbgmodel.IDebugHostModule3.FindContainingSymbolByRVA
tech.root: debugger
title: IDebugHostModule3::FindContainingSymbolByRVA
ms.date: 02/24/2025
targetos: Windows
description: The FindSymbolByRVA method, when called on a module, retrieves a symbol at a given relative virtual address within the module.
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
 - IDebugHostModule3::FindContainingSymbolByRVA
f1_keywords:
 - IDebugHostModule3::FindContainingSymbolByRVA
 - dbgmodel/IDebugHostModule3::FindContainingSymbolByRVA
dev_langs:
 - c++
helpviewer_keywords:
 - FindContainingSymbolByRVA
---

## -description

The FindSymbolByRVA method will find a single matching symbol at the given relative virtual address within the module. If there is not a single symbol at the supplied RVA (e.g.: there are multiple matches), an error will be returned by this method. Note that this method will prefer returning a private symbol over a symbol in the publics table.

## -parameters

### -param rva

The relative virtual address (offset) within the module for which to locate a matching symbol in the symbolic information for the module.

### -param symbol

The found symbol will be returned here.

### -param offset

The offset value.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostModule3 interface](nn-dbgmodel-idebughostmodule3.md)