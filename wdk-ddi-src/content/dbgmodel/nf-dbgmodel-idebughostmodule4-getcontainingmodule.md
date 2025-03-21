---
UID: NF:dbgmodel.IDebugHostModule4.GetContainingModule
tech.root: debugger
title: IDebugHostModule4::GetContainingModule
ms.date: 02/24/2025
targetos: Windows
description: The IDebugHostModule4::GetContainingModule method, when called on a symbol, gets the module that contains the symbol if the symbol has a containing module.
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
 - IDebugHostModule4::GetContainingModule
f1_keywords:
 - IDebugHostModule4::GetContainingModule
 - dbgmodel/IDebugHostModule4::GetContainingModule
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

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostModule4 interface](nn-dbgmodel-idebughostmodule4.md)