---
UID: NF:dbgmodel.IDebugHostContextTargetComposition.GetServiceThread
tech.root: debugger
title: IDebugHostContextTargetComposition::GetServiceThread
ms.date: 01/15/2025
targetos: Windows
description: The GetServiceThread method retrieves the thread that is associated with a particular host context.
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
 - IDebugHostContextTargetComposition::GetServiceThread
f1_keywords:
 - IDebugHostContextTargetComposition::GetServiceThread
 - dbgmodel/IDebugHostContextTargetComposition::GetServiceThread
dev_langs:
 - c++
helpviewer_keywords:
 - GetServiceThread
---

## -description

The GetServiceThread method retrieves the thread that is associated with a particular host context.

## -parameters

### -param ppThread

A pointer to a pointer variable that receives the ISvcThread interface.

## -returns

If the method succeeds, it returns S_OK. If the context refers to something above the level of a specific thread (most contexts do), this method will return an E_FAIL. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostContextTargetComposition interface](nn-dbgmodel-idebughostcontexttargetcomposition.md)