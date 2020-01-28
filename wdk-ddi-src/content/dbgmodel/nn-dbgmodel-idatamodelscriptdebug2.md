---
UID: NN:dbgmodel.IDataModelScriptDebug2
title: IDataModelScriptDebug2 (dbgmodel.h)
description: An optional interface on scripts (objects which implement IDataModelScript).
ms.assetid: 29d61401-a385-4f5e-bda3-81ee79f5c5f8
ms.date: 06/11/2019
f1_keywords:
 - "dbgmodel/IDataModelScriptDebug2"
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
- IDataModelScriptDebug2
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebug2 interface

## -description

An optional interface on scripts (objects which implement [IDataModelScript](nn-dbgmodel-idatamodelscript.md)).  If this interface is supported, the script provider has a debug engine capable of some limited form of 'script debugging'.  This may include stepping, setting breakpoints, inspecting data, etc...

This version 2 of the interface supports all of the previous methods with identical signatures and includes additional new methods that provide added functionality. The new methods are listed in the header at the end of the section for that interface.

## -inheritance
IDataModelScriptDebug2 interits from [IDataModelScriptDebug](nn-dbgmodel-idatamodelscriptdebug.md). 
## -remarks

The infrastructure for script providers in the data model also provides a concept around debugging scripts. Any script that wishes to expose debugging capabilities to the debug host and the debugger application hosting the data model can do so by having debuggable scripts implement the [IDataModelScriptDebug](nn-dbgmodel-idatamodelscriptdebug.md) interface in addition to the [IDataModelScript](nn-dbgmodel-idatamodelscript.md) interface. The presence of this interface on the script indicates to the infrastructure that it is debuggable. 

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
