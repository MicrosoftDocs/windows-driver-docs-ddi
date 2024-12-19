---
UID: NF:dbgmodel.IDebugHostContextAlternator.SwitchBack
tech.root: debugger
title: IDebugHostContextAlternator::SwitchBack
ms.date: 12/16/2024
targetos: Windows
description: The SwitchBack method restores the debugger engine context to its previous state, reverting any temporary context changes made by the SwitchTo method.
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
 - IDebugHostContextAlternator::SwitchBack
f1_keywords:
 - IDebugHostContextAlternator::SwitchBack
 - dbgmodel/IDebugHostContextAlternator::SwitchBack
dev_langs:
 - c++
helpviewer_keywords:
 - SwitchBack
---

## -description

The SwitchBack method restores the debugger engine context to its previous state, reverting any temporary context changes made by the [SwitchTo method](nf-dbgmodel-idebughostcontextalternator-switchto.md). This allows the debugger to return to its original context, resuming normal operation.

## -returns

## -remarks

Using the SwitchBack method is crucial for maintaining debugging consistency and continuity. Developers should invoke this method after using SwitchTo for a temporary context switch, especially if full access to the original context's functionalities is necessary.

## -see-also

[IDebugHostContextAlternator interface](nn-dbgmodel-idebughostcontextalternator.md)