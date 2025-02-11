---
UID: NF:dbgmodel.IDebugHostFunctionLocalDetails.GetName
tech.root: debugger
title: IDebugHostFunctionLocalDetails::GetName
ms.date: 01/29/2025
targetos: Windows
description: The GetName method retrieves the name of the local variable.
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
 - IDebugHostFunctionLocalDetails::GetName
f1_keywords:
 - IDebugHostFunctionLocalDetails::GetName
 - dbgmodel/IDebugHostFunctionLocalDetails::GetName
dev_langs:
 - c++
helpviewer_keywords:
 - GetName
---

## -description

The GetName method retrieves the name of the local variable.

## -parameters

### -param name

A pointer to a BSTR variable. This parameter receives the name of the local variable.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostFunctionLocalDetails interface](nn-dbgmodel-idebughostfunctionlocaldetails.md)