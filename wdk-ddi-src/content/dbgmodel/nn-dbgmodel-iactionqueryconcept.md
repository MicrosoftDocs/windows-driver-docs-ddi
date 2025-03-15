---
UID: NN:dbgmodel.IActionQueryConcept
tech.root: debugger
title: IActionQueryConcept (dbgmodel.h)
ms.date:  10/31/2024
targetos: Windows
description: A concept which is automatically implemented by the data model for any object which has (or can have) actions on it.  (dbgmodel.h)
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
 - IActionQueryConcept
f1_keywords:
 - IActionQueryConcept
 - dbgmodel/IActionQueryConcept
dev_langs:
 - c++
helpviewer_keywords:
 - IActionQueryConcept
---

## -description

A concept which is automatically implemented by the data model for any object which has (or can have) actions
on it. The enumerator returned from this concept will aggregate all actions implemented via metadata keys on
 methods and those implemented via direct support of IActionableConcept anywhere on the object.

Clients should *NEVER* implement this concept -- only query for it.

## -inheritance

IActionQueryConcept inherits from IUnknown.

## -remarks

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
