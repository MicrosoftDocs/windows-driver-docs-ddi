---
UID: NF:dbgmodel.IDebugHostContextExtensibility.ReadExtensionData
tech.root: debugger
title: IDebugHostContextExtensibility::ReadExtensionData
ms.date: 01/15/2025
targetos: Windows
description: The ReadExtensionData method reads extension data from the host context.
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
 - IDebugHostContextExtensibility::ReadExtensionData
f1_keywords:
 - IDebugHostContextExtensibility::ReadExtensionData
 - dbgmodel/IDebugHostContextExtensibility::ReadExtensionData
dev_langs:
 - c++
helpviewer_keywords:
 - ReadExtensionData
---

## -description

This method reads a set of extension data from a host context. This method will fail if the context does not have the particular extension blob associated with it.

## -parameters

### -param blobId

This input parameter represents the id of the blob whose data will be read from the host context.

### -param bufferSize

This input parameter represents the size of the buffer which will be used to retrieve the data from the host context.

### -param buffer

This output parameter is a pointer that points to the buffer which will be populated with the data from the host context.

## -returns

If the method succeeds, it returns S_OK. If it fails due to the context not having the particular extension blob associated with it, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostContextExtensibility interface](nn-dbgmodel-idebughostcontextextensibility.md)