---
UID: NF:dbgmodel.IDebugHostContextTargetComposition.GetServiceProcess
tech.root: debugger
title: IDebugHostContextTargetComposition::GetServiceProcess
ms.date: 01/15/2025
targetos: Windows
description: The GetServiceProcess method retrieves the process that is associated with a particular host context.
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
 - IDebugHostContextTargetComposition::GetServiceProcess
f1_keywords:
 - IDebugHostContextTargetComposition::GetServiceProcess
 - dbgmodel/IDebugHostContextTargetComposition::GetServiceProcess
dev_langs:
 - c++
helpviewer_keywords:
 - GetServiceProcess
---

## -description

The GetServiceProcess method retrieves the process that is associated with a particular host context.

## -parameters

### -param ppProcess

A pointer to a pointer variable that receives the ISvcProcess interface.

## -returns

If the method succeeds, it returns S_OK. If the context refers to something above the level of a specific process, this method will return an E_FAIL. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostContextTargetComposition interface](nn-dbgmodel-idebughostcontexttargetcomposition.md)