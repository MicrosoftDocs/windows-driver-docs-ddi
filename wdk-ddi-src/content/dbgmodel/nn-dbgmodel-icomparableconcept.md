---
UID: NN:dbgmodel.IComparableConcept
title: IComparableConcept (dbgmodel.h)
description: Compares this object to another (of arbitrary type).  If the comparison cannot be performed, E_NOT_SET should be returned.
ms.assetid: ddbad055-aafe-4ba0-8265-1b9216610f20
ms.date: 07/13/2018
keywords: ["IComparableConcept interface"]
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
 - IComparableConcept
 - dbgmodel/IComparableConcept
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IComparableConcept
---

# IComparableConcept interface


## -description

Compares this object to another (of arbitrary type).  If the comparison cannot be performed, E_NOT_SET should be returned.

## -inheritance

IComparableConcept interits from IUnknown.

## -remarks

The return value passed in comparison result has the following meaning:

```text
< 0 : contextObject < otherObject
0 : contextObject == otherObject
> 0 : contextObject > otherObject
```

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)

