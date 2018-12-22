---
UID: NF:dbgmodel.IDataModelConcept.GetName
title: IDataModelConcept::GetName
description: If a given data model is registered under a default name via the RegisterNamedModel method, the registered data model's IDataModelConcept interface must return that name from this method.
ms.assetid: 963ade84-243f-419e-979e-6f8aed2ff596
ms.date: 09/21/2018
ms.topic: method
ms.keywords: IDataModelConcept::GetName, GetName, IDataModelConcept.GetName, IDataModelConcept::GetName, IDataModelConcept.GetName
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
-	IDataModelConcept.GetName
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelConcept::GetName


## -description

If a given data model is registered under a default name via the RegisterNamedModel method, the registered data model's IDataModelConcept interface must return that name from this method. Note that it is perfectly legitimate for a model to be registered under multiple names (the default or best one should be returned here). A model may be completely unnamed (so long as it is not registered under a name). In such circumstances, the GetName method should return E_NOTIMPL. 

## -parameters

### -param modelName
The model name should be returned in this argument as a string allocated via the SysAllocString method.

## -returns
This method returns HRESULT which indicates success or failure. A model which is unnamed should return E_NOTIMPL.

## -remarks

## -see-also

[IDataModelConcept interface](nn-dbgmodel-idatamodelconcept.md)
