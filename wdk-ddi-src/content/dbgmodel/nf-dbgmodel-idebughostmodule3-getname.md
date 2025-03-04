---
UID: NF:dbgmodel.IDebugHostModule3.GetName
tech.root: debugger
title: IDebugHostModule3::GetName
ms.date: 02/24/2025
targetos: Windows
description: The IDebugHostModule3::GetName method, when called on a symbol, gets the name of the symbol if it has a name.
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
 - IDebugHostModule3::GetName
f1_keywords:
 - IDebugHostModule3::GetName
 - dbgmodel/IDebugHostModule3::GetName
dev_langs:
 - c++
helpviewer_keywords:
 - GetName
---

## -description

Returns the name of the symbol if the symbol has a name.  If the symbol does not have a name, an error is returned.

## -parameters

### -param symbolName

The name of the symbol will be returned here as a string allocated via the SysAllocString method.  The caller is responsible for freeing the allocated string via the SysFreeString method.

## -returns

This method returns HRESULT that indicates success or failure.

## -see-also

[IDebugHostModule3 interface](nn-dbgmodel-idebughostmodule3.md)
