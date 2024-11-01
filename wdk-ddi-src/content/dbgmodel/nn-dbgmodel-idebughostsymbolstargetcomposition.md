---
UID: NN:dbgmodel.IDebugHostSymbolsTargetComposition
tech.root: debugger
title: IDebugHostSymbolsTargetComposition
ms.date: 10/31/2024
targetos: Windows
description: IDebugHostSymbolsTargetComposition provides interfaces which bridges the extensibility of the upper edge interfaces (the data model) with those of the lower edge (target composition) for symbols. (dbgmodel.h)
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
 - IDebugHostSymbolsTargetComposition
f1_keywords:
 - IDebugHostSymbolsTargetComposition
 - dbgmodel/IDebugHostSymbolsTargetComposition
dev_langs:
 - c++
helpviewer_keywords:
 - IDebugHostSymbolsTargetComposition
---

## -description

IDebugHostSymbolsTargetComposition provides interfaces which bridges the extensibility of the upper edge interfaces (the data model) with those of the lower edge (target composition) for symbols.

## -inheritance

IDebugHostSymbolsTargetComposition inherits from IUnknown.

## -remarks

This and IDebugHostContextTargetComposition are optional Bridge Interfaces to Target Composition Interfaces.

A debug host which only supports the data model layer need not support any of these interfaces.  A debug host which supports both the data model layer and target composition layer of extensibility supports these to bridge between the two layers.

## -see-also

[Debugger Data Model C++ Interfaces Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
