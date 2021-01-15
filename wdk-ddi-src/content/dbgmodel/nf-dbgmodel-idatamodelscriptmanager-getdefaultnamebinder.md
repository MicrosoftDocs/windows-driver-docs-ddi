---
UID: NF:dbgmodel.IDataModelScriptManager.GetDefaultNameBinder
title: IDataModelScriptManager::GetDefaultNameBinder (dbgmodel.h)
description: The GetDefaultNameBinder method returns the data model's default script name binder.
ms.date: 08/20/2018
keywords: ["IDataModelScriptManager::GetDefaultNameBinder"]
ms.keywords: IDataModelScriptManager::GetDefaultNameBinder, GetDefaultNameBinder, IDataModelScriptManager.GetDefaultNameBinder, IDataModelScriptManager::GetDefaultNameBinder, IDataModelScriptManager.GetDefaultNameBinder
req.header: dbgmodel.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
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
 - IDataModelScriptManager::GetDefaultNameBinder
 - dbgmodel/IDataModelScriptManager::GetDefaultNameBinder
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelScriptManager::GetDefaultNameBinder
---

# IDataModelScriptManager::GetDefaultNameBinder


## -description

The GetDefaultNameBinder method returns the data model's default script name binder. A name binder is a component which resolves a name within the context of an object. For instance, given the expression "foo.bar", a name binder is called upon to resolve the name bar in the context of object foo. The binder returned here follows a set of default rules for the data model. Script providers can use this binder to provide consistency in name resolution across providers.

## -parameters

### -param ppNameBinder

The default name binder will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

The [IDataModelNameBinder](nn-dbgmodel-idatamodelnamebinder.md) topic provides more information on how a name binder can associate names in a context with objects or symbols.

## -see-also

[IDataModelScriptManager interface](nn-dbgmodel-idatamodelscriptmanager.md)

