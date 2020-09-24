---
UID: NN:dbgmodel.IRawEnumerator
title: IRawEnumerator (dbgmodel.h)
description: An interface which enumerates the raw children (base classes, fields, etc...) of an object (and their values and associated metadata).
ms.assetid: 9ffd4c68-726e-41a9-a5d7-523d039dc72f
ms.date: 07/16/2018
keywords: ["IRawEnumerator interface"]
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
 - IRawEnumerator
 - dbgmodel/IRawEnumerator
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IRawEnumerator
---

# IRawEnumerator interface


## -description

An interface which enumerates the raw children (e.g.: base classes, fields, etc...) of an object (and their values and associated metadata).  A raw enumerator can be acquired through the EnumerateRawValues or EnumerateRawReferences methods on [IModelObject](nn-dbgmodel-imodelobject.md).

## -inheritance

IRawEnumerator interits from IUnknown.

## -remarks

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)