---
UID: NF:dbgmodel.IDebugHostBaseClass2.GetName
tech.root: debugger
title: IDebugHostBaseClass2::GetName
ms.date: 12/16/2024
targetos: Windows
description: The GetName method, when called on a symbol, gets the name of the symbol if it has a name.
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
 - IDebugHostBaseClass2::GetName
f1_keywords:
 - IDebugHostBaseClass2::GetName
 - dbgmodel/IDebugHostBaseClass2::GetName
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

[IDebugHostBaseClass2 interface](nn-dbgmodel-idebughostbaseclass2.md)