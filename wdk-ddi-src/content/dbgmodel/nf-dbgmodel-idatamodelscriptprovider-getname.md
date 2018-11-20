---
UID: NF:dbgmodel.IDataModelScriptProvider.GetName
title: IDataModelScriptProvider::GetName
author: windows-driver-content
description: The GetName method returns the name of the type of (or language of) scripts which the provider manages as a string allocated via the SysAllocString method.
ms.assetid: 3dc27a0b-1bdd-4dea-82ee-51d402d7d5c0
ms.date: 08/20/2018
ms.topic: method
ms.keywords: IDataModelScriptProvider::GetName, GetName, IDataModelScriptProvider.GetName, IDataModelScriptProvider::GetName, IDataModelScriptProvider.GetName
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
-	IDataModelScriptProvider.GetName
product: Windows
targetos: Windows
ms.custom: RS5
---

# IDataModelScriptProvider::GetName


## -description

The GetName method returns the name of the type of (or language of) scripts which the provider manages as a string allocated via the SysAllocString method. The caller is responsible for freeing the returned string via SysFreeString. Examples of strings which might be returned from this method are "JavaScript" or "NatVis". The returned string is likely to appear in the user interface of the debugger application which is hosting the data model. 

No two script providers may return the same name (case insensitive). 


## -parameters

### -param name

The name of the type of (or language of) scripts managed via the provider. The string is allocated via SysAllocString and the caller is responsible for freeing it via SysFreeString.


## -returns

This method returns HRESULT that indicates success or failure.

## -remarks


## -see-also

[IDataModelScriptProvider interface](nn-dbgmodel-idatamodelscriptprovider.md)
