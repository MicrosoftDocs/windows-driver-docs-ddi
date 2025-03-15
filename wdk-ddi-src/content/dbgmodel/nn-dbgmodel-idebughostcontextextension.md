---
UID: NN:dbgmodel.IDebugHostContextExtension
tech.root: debugger
title: IDebugHostContextExtension
ms.date: 10/31/2024
targetos: Windows
description: An optional dbgmodel interface on host contexts that allows for extensibility based modification.
prerelease: false
req.assembly: 
req.construct-type: iface
req.ddi-compliance: 
req.header: dbgmodel.h
req.idl: 
req.include-header: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostContextExtension
f1_keywords:
 - IDebugHostContextExtension
 - dbgmodel/IDebugHostContextExtension
dev_langs:
 - c++
helpviewer_keywords:
 - IDebugHostContextExtension
---

## -description

An optional "interface" on host contexts that allows for extensibility based modification.  

This interface is *NEVER* QI'able off an IDebugHostContext.  Changes must be done via a QI for IDebugHostContextExtensibility and cloning an existing context (with optional additions).  Once this interface is released, it can never be reacquired.

## -inheritance

IDebugHostContextExtension inherits from IUnknown.

## -remarks

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
