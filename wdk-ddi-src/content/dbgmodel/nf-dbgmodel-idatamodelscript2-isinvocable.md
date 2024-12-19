---
UID: NF:dbgmodel.IDataModelScript2.IsInvocable
tech.root: debugger
title: IDataModelScript2::IsInvocable
ms.date: 12/16/2024
targetos: Windows
description: The IsInvocable method returns whether or not the script is invocable -- that is, whether it has a "main function" as defined by its language or provider.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgmodel.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelScript2::IsInvocable
f1_keywords:
 - IDataModelScript2::IsInvocable
 - dbgmodel/IDataModelScript2::IsInvocable
dev_langs:
 - c++
helpviewer_keywords:
 - IsInvocable
---

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

[IDataModelScript2 interface](nn-dbgmodel-idatamodelscript2.md)