---
UID: NF:dbgmodel.IDebugHostExtensibility3.ReleaseHostContextExtension
tech.root: debugger
title: IDebugHostExtensibility3::ReleaseHostContextExtension
ms.date: 01/20/2025
targetos: Windows
description: The ReleaseHostContextExtension method is used to release the reservation of a host context blob as acquired from the ExtendHostContext method
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
 - IDebugHostExtensibility3::ReleaseHostContextExtension
f1_keywords:
 - IDebugHostExtensibility3::ReleaseHostContextExtension
 - dbgmodel/IDebugHostExtensibility3::ReleaseHostContextExtension
dev_langs:
 - c++
helpviewer_keywords:
 - ReleaseHostContextExtension
---

## -description

The ReleaseHostContextExtension method is used to release the reservation of a host context blob as acquired from the [ExtendHostContext method](nn-dbgmodel-idebughostextensibility3-extendhostcontext.md).

## -parameters

### -param blobId

A ULONG variable that is the unique identifier of the blob to be released.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostExtensibility3 interface](nn-dbgmodel-idebughostextensibility3.md)