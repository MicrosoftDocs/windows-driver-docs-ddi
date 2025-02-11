---
UID: NF:dbgmodel.IDebugHostFunctionLocalDetails2.GetType
tech.root: debugger
title: IDebugHostFunctionLocalDetails2::GetType
ms.date: 01/29/2025
targetos: Windows
description: The GetType method retrieves the type of the local variable.
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
 - IDebugHostFunctionLocalDetails2::GetType
f1_keywords:
 - IDebugHostFunctionLocalDetails2::GetType
 - dbgmodel/IDebugHostFunctionLocalDetails2::GetType
dev_langs:
 - c++
helpviewer_keywords:
 - GetType
---

## -description

The GetType method retrieves the type of the local variable.

## -parameters

### -param localType

A pointer to a pointer variable that receives the IDebugHostType interface of the local variable type.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostFunctionLocalDetails2 interface](nn-dbgmodel-idebughostfunctionlocaldetails2.md)