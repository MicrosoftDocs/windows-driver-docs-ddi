---
UID: NN:dbgmodel.IDebugHostExtensibility
title: IDebugHostExtensibility (dbgmodel.h)
description: The extensibility interface to the underlying debugger.
ms.assetid: ca0b53b7-9e3a-4dca-ab84-0e147006ac32
ms.date: 07/13/2018
keywords: ["IDebugHostExtensibility interface"]
req.header: dbgmodel.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDebugHostExtensibility
 - dbgmodel/IDebugHostExtensibility
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostExtensibility
---

# IDebugHostExtensibility interface


## -description

The extensibility interface to the underlying debugger.

## -inheritance

IDebugHostExtensibility interits from IUnknown.

## -remarks

Certain functionality of the debug host is optionally subject to extensibility. This may, for instance, include the expression evaluator. The IDebugHostExtensibility interface is the means by which these extensibility points are accessed.

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)