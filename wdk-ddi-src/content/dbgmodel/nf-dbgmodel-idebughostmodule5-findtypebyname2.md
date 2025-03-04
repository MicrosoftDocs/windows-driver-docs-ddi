---
UID: NF:dbgmodel.IDebugHostModule5.FindTypeByName2
tech.root: debugger
title: IDebugHostModule5::FindTypeByName2
ms.date: 02/24/2025
targetos: Windows
description: The FindTypeByName2 method finds a type by name within the module. If an enclosing symbol is given, the type is looked for by name within that enclosing symbol; otherwise, the type is looked for globally.
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
 - IDebugHostModule5::FindTypeByName2
f1_keywords:
 - IDebugHostModule5::FindTypeByName2
 - dbgmodel/IDebugHostModule5::FindTypeByName2
dev_langs:
 - c++
helpviewer_keywords:
 - FindTypeByName2
---

## -description

The FindTypeByName2 method finds a type by name within the module. If an enclosing symbol is given, the type is looked for by name within that enclosing symbol; otherwise, the type is looked for globally.

## -parameters

### -param pEnclosingSymbol

Optional parameter. If provided, the method looks for the type within this enclosing symbol.

### -param typeName

The name of the type to search for.

### -param type

Pointer to where the found IDebugHostType object will be stored.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostModule5 interface](nn-dbgmodel-idebughostmodule5.md)