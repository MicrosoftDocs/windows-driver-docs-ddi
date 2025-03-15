---
UID: NN:dbgmodel.IDeconstructableConcept
tech.root: debugger
title: IDeconstructableConcept
ms.date: 10/31/2024
targetos: Windows
description: A concept that a data model can support in order to decompose an object into a set of arguments which can be passed to the constructable concept in order to create a new identical instance of the object (dbgmodel.h).
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
 - IDeconstructableConcept
f1_keywords:
 - IDeconstructableConcept
 - dbgmodel/IDeconstructableConcept
dev_langs:
 - c++
helpviewer_keywords:
 - IDeconstructableConcept
---

## -description

A concept that a data model can support in order to decompose an object into a set of arguments which can be passed to the constructable concept in order to create a new identical instance of the object (short any extensions which were manually attached).

## -inheritance

IDeconstructableConcept inherits from IUnknown.

## -remarks

An object which is indexable via a custom "value type" can support the deconstructable concept on object in order to allow a debugger engine to "serialize" enough information to get the indexer back in a subsequent invocation.

Any object which supports the deconstructable concept should have a parent model attached which supports the constructable concept.  That model should be registered under the name returned from the GetConstructableModelName method on this interface.  The inverse is not necessarily true.

## -see-also

[Debugger Data Model C++ Interfaces Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
