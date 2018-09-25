---
UID: NF:dbgmodel.IDataModelScriptTemplate.GetDescription
title: IDataModelScriptTemplate::GetDescription
author: windows-driver-content
description: TBD
ms.assetid: 1335191d-ca6c-4f68-80c1-a0116944f8c8
ms.author: windowsdriverdev
ms.date: 08/21/2018
ms.topic: method
ms.keywords: IDataModelScriptTemplate::GetDescription, GetDescription, IDataModelScriptTemplate.GetDescription, IDataModelScriptTemplate::GetDescription, IDataModelScriptTemplate.GetDescription
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
-	IDataModelScriptTemplate.GetDescription
product: Windows
targetos: Windows


---

# IDataModelScriptTemplate::GetDescription


## -description

The GetDescription method returns a description of the template. Such description would be presented to the user in more descriptive interfaces to help the user understand what the template is designed to do. The template may return E_NOTIMPL from this method if it does not have a description. 

## -parameters

### -param templateDescription

The description of the template is returned here as a string allocated via the SysAllocString function. The caller is responsible for freeing this string with SysFreeString.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelScriptTemplate interface](nn-dbgmodel-idatamodelscripttemplate.md)