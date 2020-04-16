---
UID: NN:dbgmodel.IDebugHostModuleSignature
title: IDebugHostModuleSignature (dbgmodel.h)
description: Represents a module signature -- a definition which will match a set of modules by name and/or version.
ms.assetid: 77ea2e07-153d-4477-bb8f-626d9fac797b
ms.date: 07/13/2018
keywords: ["IDebugHostModuleSignature interface"]
f1_keywords:
 - "dbgmodel/IDebugHostModuleSignature"
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
topic_type: 
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDebugHostModuleSignature
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostModuleSignature interface

## -description

Represents a module signature -- a definition which will match a set of modules by name and/or version.


## -inheritance
IDebugHostModuleSignature interits from IUnknown. 
## -remarks

Module signatures represent a means to check whether a given module meets a set of criteria regarding naming and versioning. A module signature is created via the CreateModuleSignature method on [IDebugHostSymbols](nn-dbgmodel-idebughostsymbols.md). It can match the module name, and an optional range of version numbers for the module. Once such a signature is created, the client receives an IDebugHostModuleSignature interface.

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
