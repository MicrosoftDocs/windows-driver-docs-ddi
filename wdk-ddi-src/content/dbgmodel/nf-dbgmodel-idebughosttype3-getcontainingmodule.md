---
UID: NF:dbgmodel.IDebugHostType3.GetContainingModule
tech.root: debugger
title: IDebugHostType3::GetContainingModule
ms.date: 01/26/2025
targetos: Windows
description: The GetContainingModule method, when called on a symbol, gets the module that contains the symbol if the symbol has a containing module.
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
 - IDebugHostType3::GetContainingModule
f1_keywords:
 - IDebugHostType3::GetContainingModule
 - dbgmodel/IDebugHostType3::GetContainingModule
dev_langs:
 - c++
helpviewer_keywords:
 - GetContainingModule
---

## -description

Returns the module which contains this symbol if the symbol has a containing module.  If the symbol does not have a containing module, an error is returned.

## -parameters

### -param containingModule

The module which contains the symbol will be returned here.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)
