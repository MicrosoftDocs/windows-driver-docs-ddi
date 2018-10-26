---
UID: NF:dbgmodel.IDataModelScriptProviderEnumerator.GetNext
title: IDataModelScriptProviderEnumerator::GetNext
author: windows-driver-content
description: Gets the next script provider which is being enumerated and moves the enumerator to the next position. 
ms.assetid: d405006e-12bd-4540-be64-48e98a8651c1
ms.date: 10/05/2018
ms.topic: method
ms.keywords: IDataModelScriptProviderEnumerator::GetNext, GetNext, IDataModelScriptProviderEnumerator.GetNext, IDataModelScriptProviderEnumerator::GetNext, IDataModelScriptProviderEnumerator.GetNext
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
-	IDataModelScriptProviderEnumerator.GetNext
product: Windows
targetos: Windows
tech.root: debugger
---

# IDataModelScriptProviderEnumerator::GetNext


## -description

The GetNext method will move the enumerator forward one element and return the script provider which is at that element. When the enumerator hits the end of enumeration, E_BOUNDS will be returned. Calling the GetNext method after receiving this error will continue to return E_BOUNDS indefinitely. 

## -parameters

### -param provider
The next script provider registered with the script manager will be returned here.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelScriptProviderEnumerator interface](nn-dbgmodel-idatamodelscriptproviderenumerator.md)
