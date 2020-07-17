---
UID: NF:dbgmodel.IDataModelScript.IsInvocable
title: IDataModelScript::IsInvocable (dbgmodel.h)
description: The IsInvocable method returns whether or not the script is invocable -- that is, whether it has a "main function" as defined by its language or provider. 
ms.assetid: ff8dc281-89db-4ef5-afaa-f022015a6247
ms.date: 08/20/2018
keywords: ["IDataModelScript::IsInvocable"]
f1_keywords:
 - "dbgmodel/IDataModelScript.IsInvocable"
 - "IDataModelScript.IsInvocable"
ms.keywords: IDataModelScript::IsInvocable, IsInvocable, IDataModelScript.IsInvocable, IDataModelScript::IsInvocable, IDataModelScript.IsInvocable
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
- IDataModelScript.IsInvocable
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScript::IsInvocable


## -description

The IsInvocable method returns whether or not the script is invocable -- that is, whether it has a "main function" as defined by its language or provider. Such a "main function" is conceptually something that the script author would want called if an imaginary "Execute Script" button were pressed in a user interface. 

This method is only legal to call after a successful call to the Execute method. Calling this method when a script has not yet executed (or has unlinked) is illegal and should produce an error. 


## -parameters

### -param isInvocable

An indication of whether the script is invocable is returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks



## -see-also

[IDataModelScript interface](nn-dbgmodel-idatamodelscript.md)
