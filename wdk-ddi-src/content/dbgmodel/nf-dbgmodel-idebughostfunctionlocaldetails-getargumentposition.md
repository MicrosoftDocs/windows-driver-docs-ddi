---
UID: NF:dbgmodel.IDebugHostFunctionLocalDetails.GetArgumentPosition
tech.root: debugger
title: IDebugHostFunctionLocalDetails::GetArgumentPosition
ms.date: 01/29/2025
targetos: Windows
description: The GetArgumentPosition method obtains the position of the function argument within the argument list.
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
 - IDebugHostFunctionLocalDetails::GetArgumentPosition
f1_keywords:
 - IDebugHostFunctionLocalDetails::GetArgumentPosition
 - dbgmodel/IDebugHostFunctionLocalDetails::GetArgumentPosition
dev_langs:
 - c++
helpviewer_keywords:
 - GetArgumentPosition
---

## -description

The GetArgumentPosition method obtains the position of the function argument within the argument list. This method will fail on any local which does not return LocalArgument from the [GetLocalKind() method](nf-dbgmodel-idebughostfunctionlocaldetails-getlocalkind.md).

## -parameters

### -param argPosition

A pointer to a ULONG64 variable. This parameter receives the position of the argument within the argument list.

## -returns

f the method succeeds, it returns S_OK. If the local does not return LocalArgument from the GetLocalKind() method, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostFunctionLocalDetails interface](nn-dbgmodel-idebughostfunctionlocaldetails.md)