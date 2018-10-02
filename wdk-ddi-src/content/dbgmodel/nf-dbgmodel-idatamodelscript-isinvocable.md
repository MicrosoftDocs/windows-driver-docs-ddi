---
UID: NF:dbgmodel.IDataModelScript.IsInvocable
title: IDataModelScript::IsInvocable
author: windows-driver-content
description: TBD
ms.assetid: ff8dc281-89db-4ef5-afaa-f022015a6247
ms.author: windowsdriverdev
ms.date: 08/20/2018
ms.topic: method
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
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDataModelScript.IsInvocable
product: Windows
targetos: Windows
tech.root: debugger
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
