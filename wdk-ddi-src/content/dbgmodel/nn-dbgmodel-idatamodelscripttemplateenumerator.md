---
UID: NN:dbgmodel.IDataModelScriptTemplateEnumerator
title: IDataModelScriptTemplateEnumerator (dbgmodel.h)
description: An enumerator which enumerates an available set of script templates.
ms.assetid: 7d5f9983-35d8-4983-94af-3419f843b838
ms.date: 07/13/2018
keywords: ["IDataModelScriptTemplateEnumerator interface"]
f1_keywords:
 - "dbgmodel/IDataModelScriptTemplateEnumerator"
 - "IDataModelScriptTemplateEnumerator"
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
- IDataModelScriptTemplateEnumerator
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptTemplateEnumerator interface

## -description

An enumerator which enumerates an available set of script templates.

An enumerator interface that the script provider implements in order to advertise all the various templates it supports.


## -inheritance
IDataModelScriptTemplateEnumerator interits from IUnknown. 
## -remarks

A script provider can provide one or more templates which pre-fill content into newly created scripts in some user interface. If any of these templates are provided, the script provider must implement an enumerator over them which is returned upon a call to the EnumerateTemplates method. 
## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
