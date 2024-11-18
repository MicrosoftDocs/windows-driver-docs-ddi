---
UID: NN:dbgmodel.IConstructableConcept
tech.root: debugger
title: IConstructableConcept (dbgmodel.h)
ms.date: 10/31/2024
targetos: Windows
description: A concept that a data model can support in order to allow for construction of the object. (dbgmodel.h)
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
 - IConstructableConcept
f1_keywords:
 - IConstructableConcept
 - dbgmodel/IConstructableConcept
dev_langs:
 - c++
helpviewer_keywords:
 - IConstructableConcept
---

## -description

A concept that a data model can support in order to allow for construction of the object.

Such a data model *MUST* support IDataModelConcept and *MUST* be registered under a name that is returned from IDataModelConcept::GetName.

## -inheritance

IConstructableConcept inherits from IUnknown.


## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
