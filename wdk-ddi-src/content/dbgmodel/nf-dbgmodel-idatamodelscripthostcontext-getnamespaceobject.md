---
UID: NF:dbgmodel.IDataModelScriptHostContext.GetNamespaceObject
title: IDataModelScriptHostContext::GetNamespaceObject (dbgmodel.h)
description: The GetNamespaceObject method returns an object into which the script provider can place any bridges between the data model and the script.
ms.assetid: 10b093f4-f047-4710-8bbe-aa9ce3973021
ms.date: 09/10/2018
keywords: ["IDataModelScriptHostContext::GetNamespaceObject"]
ms.keywords: IDataModelScriptHostContext::GetNamespaceObject, GetNamespaceObject, IDataModelScriptHostContext.GetNamespaceObject, IDataModelScriptHostContext::GetNamespaceObject, IDataModelScriptHostContext.GetNamespaceObject
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
 - IDataModelScriptHostContext::GetNamespaceObject
 - dbgmodel/IDataModelScriptHostContext::GetNamespaceObject
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelScriptHostContext.GetNamespaceObject
---

# IDataModelScriptHostContext::GetNamespaceObject


## -description

The GetNamespaceObject method returns an object into which the script provider can place any bridges between the data model and the script. It is here, for instance, that the script provider might place data model method objects ([IModelMethod](nn-dbgmodel-imodelmethod.md) interfaces boxed into [IModelObject](nn-dbgmodel-imodelobject.md)) whose implementation calls into correspondingly named functions in the script.

## -parameters

### -param namespaceObject

A data model object which can be used as the representation of the namespace of the script.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDataModelScriptHostContext interface](nn-dbgmodel-idatamodelscripthostcontext.md)

