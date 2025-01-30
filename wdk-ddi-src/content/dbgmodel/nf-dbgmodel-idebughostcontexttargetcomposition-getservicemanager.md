---
UID: NF:dbgmodel.IDebugHostContextTargetComposition.GetServiceManager
tech.root: debugger
title: IDebugHostContextTargetComposition::GetServiceManager
ms.date: 01/15/2025
targetos: Windows
description: The GetServiceManager method retrieves the service manager container that is associated with a particular host context.
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
 - IDebugHostContextTargetComposition::GetServiceManager
f1_keywords:
 - IDebugHostContextTargetComposition::GetServiceManager
 - dbgmodel/IDebugHostContextTargetComposition::GetServiceManager
dev_langs:
 - c++
helpviewer_keywords:
 - GetServiceManager
---

## -description

The GetServiceManager method retrieves the service manager container that is associated with a particular host context.

## -parameters

### -param ppServiceManager

A pointer to a pointer variable that receives the IDebugServiceManager interface.

## -returns

If the method succeeds, it returns S_OK. If the context refers to something "debugger centric" above the level of a specific debug target, this method will return an E_FAIL. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostContextTargetComposition interface](nn-dbgmodel-idebughostcontexttargetcomposition.md)