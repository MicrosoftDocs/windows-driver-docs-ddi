---
UID: NF:dbgmodel.IDataModelScriptManager.UnregisterScriptProvider
title: IDataModelScriptManager::UnregisterScriptProvider (dbgmodel.h)
description: The UnregisterScriptProvider method undoes a call to the RegisterScriptProvider method. 
ms.assetid: ab48f873-3651-41c6-9b7d-6fa720e052ee
ms.date: 08/20/2018
ms.topic: method
ms.keywords: IDataModelScriptManager::UnregisterScriptProvider, UnregisterScriptProvider, IDataModelScriptManager.UnregisterScriptProvider, IDataModelScriptManager::UnregisterScriptProvider, IDataModelScriptManager.UnregisterScriptProvider
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
topic_type: 
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDataModelScriptManager.UnregisterScriptProvider
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptManager::UnregisterScriptProvider


## -description

The UnregisterScriptProvider method undoes a call to the RegisterScriptProvider method. The name and file extension given by the inpassed script provider will no longer be associated with it. It is important to note that there may be a significant number of outstanding COM references to the script provider even after unregistration. This method only prevents the loading/creation of scripts of the type that the given script provider manages. If a script loaded by that provider is still loaded or has manipulated the object model of the debugger (or data model), those manipulations may still have references back into the script. There may be data models, methods, or objects which directly reference constructs in the script. A script provider must be prepared to deal with that. 

## -parameters

### -param provider
The script provider being unregistered from the script manager. Scripts of the given type and file extension will no longer be able to be loaded/created.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks


## -see-also

[IDataModelScriptManager interface](nn-dbgmodel-idatamodelscriptmanager.md)
