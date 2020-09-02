---
UID: NN:dbgmodel.IDebugHostConstant
title: IDebugHostConstant (dbgmodel.h)
description: Represents a constant within symbolic information (a non-type template argument in C++).
ms.assetid: 87e25e99-ea64-4cda-8cae-fd38ec9c3343
ms.date: 07/13/2018
keywords: ["IDebugHostConstant interface"]
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
 - IDebugHostConstant
 - dbgmodel/IDebugHostConstant
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostConstant
---

# IDebugHostConstant interface


## -description

Represents a constant within symbolic information (e.g.: a non-type template argument in C++).

## -inheritance

IDebugHostConstant interits from [IDebugHostSymbol](nn-dbgmodel-idebughostsymbol.md).

## -remarks

For locations where constant values are present in symbolic information (where a particular value is a symbol which may or may not be a constant value), the IDebugHostConstant interface expresses the notion of such a constant. This is typically used in places like template arguments where a given argument is typically a type but may instead be a non-type template argument (e.g.: a constant).

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)

