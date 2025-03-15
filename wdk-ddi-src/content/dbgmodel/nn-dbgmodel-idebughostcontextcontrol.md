---
UID: NN:dbgmodel.IDebugHostContextControl
tech.root: debugger
title: IDebugHostContextControl (dbgmodel.h)
ms.date: 10/31/2024
targetos: Windows
description: This dbgmodel.h interface allows to change the "current" context (the internal state) of the debugger (IDebugHostContext).
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
 - IDebugHostContextControl
f1_keywords:
 - IDebugHostContextControl
 - dbgmodel/IDebugHostContextControl
dev_langs:
 - c++
helpviewer_keywords:
 - IDebugHostContextControl
---

## -description

This interface allows to change the "current" context (the internal state) of the debugger (IDebugHostContext).

The context change can be a full change/switch (for example change the current process/thread/etx. being debugged)
or a temporary switch. The temporary change/switch of the internal state of the debugger may alter the debugger
in an inconsistent state and not all debugger functionality is available unless the change/switch is reverted back.

## -inheritance

IDebugHostContextControl inherits from IUnknown.

## -remarks

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
