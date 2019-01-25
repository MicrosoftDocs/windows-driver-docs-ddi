---
UID: NF:dbgmodel.IDataModelScriptProvider.CreateScript
title: IDataModelScriptProvider::CreateScript (dbgmodel.h)
description: The CreateScript method is called to create a new script. 
ms.assetid: 00318d22-c30d-4279-92a2-5df4b46a841a
ms.date: 08/20/2018
ms.topic: method
ms.keywords: IDataModelScriptProvider::CreateScript, CreateScript, IDataModelScriptProvider.CreateScript, IDataModelScriptProvider::CreateScript, IDataModelScriptProvider.CreateScript
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
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDataModelScriptProvider.CreateScript
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptProvider::CreateScript


## -description

The CreateScript method is called to create a new script. The script provider must return a new and empty script represented by the returned IDataModelScript interface whenever this method is called. Note that this method is called regardless of whether a user interface is creating a new blank script for editing by the user or whether the debugger application is loading a script from disk. The provider does not get involved in file I/O. It merely handles the requests from the hosting application via streams passed to methods on IDataModelScript. 


## -parameters

### -param script

A new and empty script will be returned here as a component implementing the IDataModelScript interface.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks


## -see-also

[IDataModelScriptProvider interface](nn-dbgmodel-idatamodelscriptprovider.md)
