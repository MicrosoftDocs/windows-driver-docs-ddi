---
UID: NN:dbgmodel.IDataModelScriptTemplateEnumerator
title: IDataModelScriptTemplateEnumerator (dbgmodel.h)
description: An enumerator which enumerates an available set of script templates.
ms.assetid: 7d5f9983-35d8-4983-94af-3419f843b838
ms.date: 07/13/2018
keywords: ["IDataModelScriptTemplateEnumerator interface"]
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
 - IDataModelScriptTemplateEnumerator
 - dbgmodel/IDataModelScriptTemplateEnumerator
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelScriptTemplateEnumerator
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

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)