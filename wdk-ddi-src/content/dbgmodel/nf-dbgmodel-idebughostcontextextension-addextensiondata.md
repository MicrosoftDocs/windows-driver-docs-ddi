---
UID: NF:dbgmodel.IDebugHostContextExtension.AddExtensionData
tech.root: debugger
title: IDebugHostContextExtension::AddExtensionData
ms.date: 01/15/2025
targetos: Windows
description: The AddExtensionData method adds extension data to a context.
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
 - IDebugHostContextExtension::AddExtensionData
f1_keywords:
 - IDebugHostContextExtension::AddExtensionData
 - dbgmodel/IDebugHostContextExtension::AddExtensionData
dev_langs:
 - c++
helpviewer_keywords:
 - AddExtensionData
---

## -description

The AddExtensionData method adds a set of extension data to a host context.

## -parameters

### -param blobId

The identifier for the blob.

### -param dataSize

The size of the data to be added.

### -param data

A pointer to the data to be added.

## -returns

This method returns ULONG.

## -remarks

## -see-also

[IDebugHostContextExtension interface](nn-dbgmodel-idebughostcontextextension.md)