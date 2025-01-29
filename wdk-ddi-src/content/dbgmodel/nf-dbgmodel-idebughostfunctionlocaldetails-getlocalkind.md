---
UID: NF:dbgmodel.IDebugHostFunctionLocalDetails.GetLocalKind
tech.root: debugger
title: IDebugHostFunctionLocalDetails::GetLocalKind
ms.date: 01/29/2025
targetos: Windows
description: The GetLocalKind method retrieves the kind of local variable that has been enumerated.
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
 - IDebugHostFunctionLocalDetails::GetLocalKind
f1_keywords:
 - IDebugHostFunctionLocalDetails::GetLocalKind
 - dbgmodel/IDebugHostFunctionLocalDetails::GetLocalKind
dev_langs:
 - c++
helpviewer_keywords:
 - GetLocalKind
---

## -description

The GetLocalKind method retrieves the kind of local variable that has been enumerated.

## -parameters

### -param kind

A pointer to a LocalKind variable. This parameter receives the kind of the local variable.

## -returns

## -remarks

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -see-also

[IDebugHostFunctionLocalDetails interface](nn-dbgmodel-idebughostfunctionlocaldetails.md)