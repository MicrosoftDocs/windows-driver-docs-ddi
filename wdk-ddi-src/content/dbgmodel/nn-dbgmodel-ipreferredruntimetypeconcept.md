---
UID: NN:dbgmodel.IPreferredRuntimeTypeConcept
title: IPreferredRuntimeTypeConcept (dbgmodel.h)
description: Interface which clients can implement if they can provide better dynamic runtime type analysis for a given type than the debugger can acquire through RTTI or v-table analysis.
ms.assetid: db2befcc-f796-49d1-b875-532adf3bec5a
ms.date: 07/16/2018
ms.topic: interface
f1_keywords:
 - "dbgmodel/IPreferredRuntimeTypeConcept"
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
- IPreferredRuntimeTypeConcept
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IPreferredRuntimeTypeConcept interface

## -description

Interface which clients can implement if they can provide better dynamic runtime type analysis for a given type than the debugger can acquire through RTTI or v-table analysis.

The object understands more about types derived from it than the underlying type system is capable of providing and would like to handle its own conversions from static to runtime type.


## -inheritance
IPreferredRuntimeTypeConcept interits from IUnknown. 
## -remarks

**Preferred Runtime Type Concept**

A debug host can be queried to make an attempt to determine the real runtime type of an object from a static type found in symbolic information. This conversion may be based on completely accurate information (e.g.: C++ RTTI) or may be based on strong heuristics such as the shape of any virtual function tables within the object. Some objects, however, cannot be converted from a static to a runtime type because they do not fit into the heuristics of the debug host (e.g.: they have no RTTI or virtual function tables). In such cases, a data model for an object can choose to override the default behavior and declare that it knows more about the "runtime type" of an object than the debug host is capable of understanding. This is done through the preferred runtime type concept and support of the IPreferredRuntimeTypeConcept interface. 


## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
