---
UID: NF:dbgmodel.IDataModelScript.GetName
title: IDataModelScript::GetName (dbgmodel.h)
description: The GetName method returns the name of the script as an allocated string via the SysAllocString function. 
ms.assetid: b3ba5728-6a17-4bdc-b22c-56349216c8a3
ms.date: 08/20/2018
keywords: ["IDataModelScript::GetName"]
f1_keywords:
 - "dbgmodel/IDataModelScript.GetName"
 - "IDataModelScript.GetName"
ms.keywords: IDataModelScript::GetName, GetName, IDataModelScript.GetName, IDataModelScript::GetName, IDataModelScript.GetName
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
- IDataModelScript.GetName
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScript::GetName


## -description

The GetName method returns the name of the script as an allocated string via the SysAllocString function. If the script does not yet have a name, the method should return a null BSTR. It should not fail in this circumstance. If the script is explicitly renamed via a call to the Rename method, the GetName method should return the newly assigned name. 

## -parameters

### -param scriptName

The name of the script should be returned here as a string allocated via SysAllocString. The caller is responsible for freeing this string via the SysFreeString method. Note that if the script is unnamed, the method should return a null BSTR as the output. It should still succeed in this case.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks


## -see-also

[IDataModelScript interface](nn-dbgmodel-idatamodelscript.md)
