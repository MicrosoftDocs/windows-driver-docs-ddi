---
UID: NN:dbgmodel.IDataModelScript
title: IDataModelScript (dbgmodel.h)
description: An abstraction of a particular script which is being managed by the provider. Each script which is loaded or being edited has a separate IDataModelScript instance.
ms.assetid: 90bb7c14-076e-45b0-9e69-24e88d74e23a
ms.date: 07/13/2018
keywords: ["IDataModelScript interface"]
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
 - IDataModelScript
 - dbgmodel/IDataModelScript
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelScript
---

# IDataModelScript interface


## -description

An abstraction of a particular script which is being managed by the provider. Each script which is loaded or being edited has a separate IDataModelScript instance.

Any script provider must implement this to represent a script managed by that provider.

## -inheritance

IDataModelScript interits from IUnknown.

## -remarks

The main interface which manages an individual script that is implemented by the provider is the IDataModelScript interface. A component implementing this interface is returned when the client wishes to create a new blank script and calls the CreateScript method on [IDataModelScriptProvider](nn-dbgmodel-idatamodelscriptprovider.md). 

Each script which is created by the provider should be in an independent silo. One script should not be able to impact another script except through explicit interaction with external objects via the data model. Two scripts, can for instance, both extend some type or concept (e.g.: the debugger's notion of what a process is). Either script can then access each other's fields via the external process object.

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)