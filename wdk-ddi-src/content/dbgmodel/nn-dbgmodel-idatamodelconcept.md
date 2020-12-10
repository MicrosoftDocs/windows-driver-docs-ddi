---
UID: NN:dbgmodel.IDataModelConcept
title: IDataModelConcept (dbgmodel.h)
description: Any object which represents a data model which is registered under a name or  is registered for a particular type signature must implement this concept and add it to the data model  object via IModelObject::SetConcept.
ms.date: 07/13/2018
keywords: ["IDataModelConcept interface"]
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
 - IDataModelConcept
 - dbgmodel/IDataModelConcept
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelConcept
---

# IDataModelConcept interface


## -description

Any object which represents a data model which is registered under a name or  is registered for a particular type signature must implement this concept and add it to the data model  object via [IModelObject](nn-dbgmodel-imodelobject.md)::SetConcept.

Clients which create data models implement this interface.  It is most frequently consumed by the data model manager itself.

## -inheritance

IDataModelConcept interits from IUnknown.

## -remarks

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
