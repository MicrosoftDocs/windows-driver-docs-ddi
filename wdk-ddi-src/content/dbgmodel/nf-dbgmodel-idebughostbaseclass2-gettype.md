---
UID: NF:dbgmodel.IDebugHostBaseClass2.GetType
tech.root: debugger
title: IDebugHostBaseClass2::GetType
ms.date: 12/16/2024
targetos: Windows
description: The GetType method, when called on a symbol, gets the type of symbol, such as int *.
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
 - IDebugHostBaseClass2::GetType
f1_keywords:
 - IDebugHostBaseClass2::GetType
 - dbgmodel/IDebugHostBaseClass2::GetType
dev_langs:
 - c++
helpviewer_keywords:
 - GetType
---

## -description

Returns the type, for example "int *", of the symbol if the symbol has a type.  If the symbol does not have a type, an error is returned.

## -parameters

### -param type

The type of the symbol will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -see-also

[IDebugHostBaseClass2 interface](nn-dbgmodel-idebughostbaseclass2.md)
