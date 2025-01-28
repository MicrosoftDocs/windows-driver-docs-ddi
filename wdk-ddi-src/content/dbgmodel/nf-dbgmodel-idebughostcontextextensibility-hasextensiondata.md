---
UID: NF:dbgmodel.IDebugHostContextExtensibility.HasExtensionData
tech.root: debugger
title: IDebugHostContextExtensibility::HasExtensionData
ms.date: 01/15/2025
targetos: Windows
description: The HasExtensionData method indicates whether a given context has a particular extension blob associated with it.
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
 - IDebugHostContextExtensibility::HasExtensionData
f1_keywords:
 - IDebugHostContextExtensibility::HasExtensionData
 - dbgmodel/IDebugHostContextExtensibility::HasExtensionData
dev_langs:
 - c++
helpviewer_keywords:
 - HasExtensionData
---

## -description

This method is used to indicate whether a given context has a particular extension blob associated with it.

## -parameters

### -param blobId

This input parameter represents the id of the blob. The function will check to see if the context has this blob associated with it.

## -returns

Returns true if the given context has the specified extension blob associated with it, otherwise returns false.

## -remarks

The HasExtensionData() method is useful for checking if a specific extension blob is associated with a context before attempting to read the extension data with [ReadExtensionData](nf-dbgmodel-idebughostcontextextensibility-readextensiondata.md).

## -see-also

[IDebugHostContextExtensibility interface](nn-dbgmodel-idebughostcontextextensibility.md)