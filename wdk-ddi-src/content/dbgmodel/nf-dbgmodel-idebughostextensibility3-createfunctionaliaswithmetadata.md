---
UID: NF:dbgmodel.IDebugHostExtensibility3.CreateFunctionAliasWithMetadata
tech.root: debugger
title: IDebugHostExtensibility3::CreateFunctionAliasWithMetadata
ms.date: 01/20/2025
targetos: Windows
description: The CreateFunctionAliasWithMetadata method is similar to CreateFunctionAlias but allows for passing metadata information about the function.
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
 - IDebugHostExtensibility3::CreateFunctionAliasWithMetadata
f1_keywords:
 - IDebugHostExtensibility3::CreateFunctionAliasWithMetadata
 - dbgmodel/IDebugHostExtensibility3::CreateFunctionAliasWithMetadata
dev_langs:
 - c++
helpviewer_keywords:
 - CreateFunctionAliasWithMetadata
---

## -description

The CreateFunctionAliasWithMetadata method is similar to [CreateFunctionAlias](nf-dbgmodel-idebughostextensibility2-createfunctionalias.md) but allows for passing metadata information about the function.

## -parameters

### -param aliasName

A pointer to a wide-character string that specifies the name of the alias.

### -param functionObject

A pointer to the IModelObject interface of the function object.

### -param metadata

A pointer to the IKeyStore interface for the metadata. This parameter is optional.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostExtensibility3 interface](nn-dbgmodel-idebughostextensibility3.md)