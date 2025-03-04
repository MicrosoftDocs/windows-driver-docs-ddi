---
UID: NF:dbgmodel.IDebugHostModule3.GetType
tech.root: debugger
title: IDebugHostModule3::GetType
ms.date: 02/24/2025
targetos: Windows
description: The IDebugHostModule3::GetType method, when called on a symbol, gets the type of symbol, such as int *.
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
 - IDebugHostModule3::GetType
f1_keywords:
 - IDebugHostModule3::GetType
 - dbgmodel/IDebugHostModule3::GetType
dev_langs:
 - c++
helpviewer_keywords:
 - GetType
---

## -description

Returns the type (e.g.: "int *") of the symbol if the symbol has a type.  If the symbol does not have a type, an error is returned.

## -parameters

### -param type

The type of the symbol will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostModule3 interface](nn-dbgmodel-idebughostmodule3.md)