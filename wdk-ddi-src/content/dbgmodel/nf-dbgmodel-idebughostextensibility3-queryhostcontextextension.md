---
UID: NF:dbgmodel.IDebugHostExtensibility3.QueryHostContextExtension
tech.root: debugger
title: IDebugHostExtensibility3::QueryHostContextExtension
ms.date: 01/20/2025
targetos: Windows
description: The QueryHostContextExtension method provides a way to lookup a context extension and its information using an identifier GUID.
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
 - IDebugHostExtensibility3::QueryHostContextExtension
f1_keywords:
 - IDebugHostExtensibility3::QueryHostContextExtension
 - dbgmodel/IDebugHostExtensibility3::QueryHostContextExtension
dev_langs:
 - c++
helpviewer_keywords:
 - QueryHostContextExtension
---

## -description

The QueryHostContextExtension method provides a way to lookup a context extension and its information using an identifier GUID.

## -parameters

### -param identifier

A REFGUID value that represents the identifier GUID of the extension.
blobId

### -param blobId

A pointer to an output ULONG variable that receives the unique identifier of the data blob associated with the queried context extension.

### -param blobSize

A pointer to an output ULONG variable that receives the size of the data blob associated with the queried context extension.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostExtensibility3 interface](nn-dbgmodel-idebughostextensibility3.md)