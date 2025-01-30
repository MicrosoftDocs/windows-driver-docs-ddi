---
UID: NF:dbgmodel.IDebugHostExtensibility3.ExtendHostContext
tech.root: debugger
title: IDebugHostExtensibility3::ExtendHostContext
ms.date: 01/20/2025
targetos: Windows
description: The ExtendHostContext method is used by hosts which support receiving arbitrary plain old data (POD) inside a host context. This method extends the notion of a host context with a specific size of POD data.
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
 - IDebugHostExtensibility3::ExtendHostContext
f1_keywords:
 - IDebugHostExtensibility3::ExtendHostContext
 - dbgmodel/IDebugHostExtensibility3::ExtendHostContext
dev_langs:
 - c++
helpviewer_keywords:
 - ExtendHostContext
---

## -description

The ExtendHostContext method is used by hosts which support receiving arbitrary plain old data (POD) inside a host context. This method extends the notion of a host context with a specific size of POD data.

## -parameters

### -param blobSize

A ULONG variable that indicates the size of the data blob to be stored in the host context.
identifier

### -param identifier

A REFGUID value that provides an identifier for the host context that gets extended.

### -param blobId

A pointer to an output ULONG variable that is used to receive a unique identifier that can be used to set and retrieve the data on any host context object.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

The data stored inside a host context must be plain intrinsic data: it cannot be a COM interface; it cannot be anything which requires destruction, and it should be as small as possible.

Unless the data is explicitly added via the [IDebugHostContextExtensibility interface](nn-dbgmodel-idebughostextensibility.md) method, no host context will contain such data.

## -see-also

[IDebugHostExtensibility3 interface](nn-dbgmodel-idebughostextensibility3.md)