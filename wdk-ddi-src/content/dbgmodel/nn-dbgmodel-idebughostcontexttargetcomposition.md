---
UID: NN:dbgmodel.IDebugHostContextTargetComposition
tech.root: debugger
title: IDebugHostContextTargetComposition
ms.date: 10/31/2024
targetos: Windows
description: An interface which bridges the extensibility of the upper edge interfaces (the data model) with those of the lower edge (target composition) for a particular host context.
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
 - IDebugHostContextTargetComposition
f1_keywords:
 - IDebugHostContextTargetComposition
 - dbgmodel/IDebugHostContextTargetComposition
dev_langs:
 - c++
helpviewer_keywords:
 - IDebugHostContextTargetComposition
---

## -description

An interface which bridges the extensibility of the upper edge interfaces (the data model) with those of the lower edge (target composition) for a particular host context.

For a debug host which supports both layers, this interface can be QI'd off any host context.

## -inheritance

IDebugHostContextTargetComposition inherits from IUnknown.

## -remarks

This and IDebugHostSymbolsTargetComposition are optional Bridge Interfaces to Target Composition Interfaces.

A debug host which only supports the data model layer need not support any of these interfaces.  A debug host which supports both the data model layer and target composition layer of extensibility supports these to bridge between the two layers.

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
