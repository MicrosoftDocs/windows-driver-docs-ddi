---
UID: NN:dbgmodel.IDebugHostScriptHost
title: IDebugHostScriptHost (dbgmodel.h)
description: An interface which the underlying debugger host must implement in order to manage data model scripts.
ms.assetid: d0376d3b-d770-44e6-8b8f-5d8cc361bf14
ms.date: 07/13/2018
ms.topic: interface
f1_keywords:
 - "dbgmodel/IDebugHostScriptHost"
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
- IDebugHostScriptHost
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostScriptHost interface

## -description

An interface which the underlying debugger host must implement in order to manage data model scripts.

The interface which indicates the capability of the debug host to take part in the scripting environment. This interface allows for the creation of contexts which inform scripting engines of where to place objects.


## -inheritance
IDebugHostScriptHost inherits from IUnknown. 
## -remarks

The IDebugHostScriptHost interface is the interface used by a script provider to get a context from the debug host for a newly created script. This context includes an object (provided by the debug host) where the script provider can place any bridges between the data model and the scripting environment. Such bridges might, for instance, be data model methods which invoke script functions. Doing this allows a caller on the data model side to invoke script methods by utilization of the Call method on [IModelMethod](nn-dbgmodel-imodelmethod.md) interface. 

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
