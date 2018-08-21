---
UID: NF:dbgmodel.IDataModelScriptTemplate.GetName
title: IDataModelScriptTemplate::GetName
author: windows-driver-content
description: TBD
ms.assetid: c5df4066-3417-43b9-bf16-a6039c73dd18
ms.author: windowsdriverdev
ms.date: 08/21/2018
ms.topic: method
ms.keywords: IDataModelScriptTemplate::GetName, GetName, IDataModelScriptTemplate.GetName, IDataModelScriptTemplate::GetName, IDataModelScriptTemplate.GetName
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
-	IDataModelScriptTemplate.GetName
product: Windows
targetos: Windows


---

# IDataModelScriptTemplate::GetName


## -description

The GetName method returns a name of the template. This may fail with E_NOTIMPL if the template does not have a name. The single default template (if such exists) is not required to have a name. All other templates are. These names may be presented in a user interface as part of a menu to select which template is to be created. 

## -parameters

### -param templateName

The name of the template is returned here as a string allocated via the SysAllocString function. The caller is responsible for freeing this string with SysFreeString.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelScriptTemplate interface](nn-dbgmodel-idatamodelscripttemplate.md)