---
UID: NF:dbgmodel.IDataModelScriptDebugClient.QueryInterface
title: IDataModelScriptDebugClient::QueryInterface (dbgmodel.h)
description: Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns. 
ms.assetid: 8d9569d1-fcd9-4bac-9e16-cf5fef74c414
ms.date: 09/10/2018
keywords: ["IDataModelScriptDebugClient::QueryInterface"]
f1_keywords:
 - "dbgmodel/IDataModelScriptDebugClient.QueryInterface"
ms.keywords: IDataModelScriptDebugClient::QueryInterface, QueryInterface, IDataModelScriptDebugClient.QueryInterface, IDataModelScriptDebugClient::QueryInterface, IDataModelScriptDebugClient.QueryInterface
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
- IDataModelScriptDebugClient.QueryInterface
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebugClient::QueryInterface


## -description

Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns. 

For more information, see [IUnknown::QueryInterface](https://docs.microsoft.com/windows/desktop/api/Unknwn/nf-unknwn-iunknown-queryinterface(refiid_void)) and [Introduction to COM](https://docs.microsoft.com/cpp/atl/introduction-to-com).


## -parameters

### -param iid
The interface ID. A pointer to an existing object provided as input. 

### -param iface
The returned pointer to the requested COM interface. 


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

Standard COM method.


## -see-also

[IDataModelScriptDebugClient interface](nn-dbgmodel-idatamodelscriptdebugclient.md)
