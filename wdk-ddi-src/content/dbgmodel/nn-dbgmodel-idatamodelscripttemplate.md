---
UID: NN:dbgmodel.IDataModelScriptTemplate
title: IDataModelScriptTemplate (dbgmodel.h)
description: Any script provider wanting to have pre-filled template content implements this interface per template.
ms.assetid: 1b0e8279-e0bf-4a27-8d48-69072054b7f8
ms.date: 07/13/2018
keywords: ["IDataModelScriptTemplate interface"]
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
 - IDataModelScriptTemplate
 - dbgmodel/IDataModelScriptTemplate
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelScriptTemplate
---

# IDataModelScriptTemplate interface


## -description

Any script provider wanting to have pre-filled template content implements this interface per template.

Script providers can provide one or more templates which serve as starting points for users to author scripts. A debugger application which provides a built-in editor can prefill new scripts with template content as advertised by the provider through this interface.

## -inheritance

IDataModelScriptTemplate interits from IUnknown.

## -remarks

Script providers that want to present pre-filled content for new scripts (e.g.: to aid users writing scripts in a debugger user interface) can do so by providing one or more script templates. Such templates are components which implement the IDataModelScriptTemplate interface and are returned via either the GetDefaultTemplate method or EnumerateTemplates method on the script provider.

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)