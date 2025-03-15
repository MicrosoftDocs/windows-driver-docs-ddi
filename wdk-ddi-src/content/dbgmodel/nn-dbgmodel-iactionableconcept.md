---
UID: NN:dbgmodel.IActionableConcept
tech.root: debugger
title: IActionableConcept (dbgmodel.h)
ms.date: 10/31/2024
targetos: Windows
description: A concept mechanism for implementing actions.  Clients may choose to either implement this interface or place appropriate metadata on effective void(void) methods. (dbgmodel.h)
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
 - IActionableConcept
f1_keywords:
 - IActionableConcept
 - dbgmodel/IActionableConcept
dev_langs:
 - c++
helpviewer_keywords:
 - IActionableConcept
---

## -description

A concept mechanism for implementing actions.  Clients may choose to either implement this interface or place
appropriate metadata on effective void(void) methods.

While this concept may be implemented, clients wishing to enumerate actions should not directly query for this
concept.  Rather, they should query for IActionQueryConcept.

## -inheritance

IActionableConcept inherits from IUnknown.

## -remarks

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)

