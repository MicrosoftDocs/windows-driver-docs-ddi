---
UID: NN:dbgmodel.IIndexableConcept
title: IIndexableConcept (dbgmodel.h)
description: Any object which is a container that supports random access retrieval of elements from given N-dimensional indexers implements IIndexableConcept.
ms.assetid: 8d92fead-7ccb-40f5-9eb7-b7d6ef5cec45
ms.date: 10/04/2018
keywords: ["IIndexableConcept interface"]
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
 - IIndexableConcept
 - dbgmodel/IIndexableConcept
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IIndexableConcept
---

# IIndexableConcept interface


## -description

Any object which is a container that supports random access retrieval of elements from given N-dimensional indexers implements this concept.

It is legal for an object to be indexable (via support of IIndexableConcept) and not iterable (via lack of support for  [IIterableConcept](nn-dbgmodel-iiterableconcept.md)).

## -inheritance

IIndexableConcept interits from IUnknown.

## -remarks

## -see-also

