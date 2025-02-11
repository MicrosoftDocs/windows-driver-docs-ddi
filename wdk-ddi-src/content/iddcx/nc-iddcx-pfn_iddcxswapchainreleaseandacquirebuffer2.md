---
UID: NC:iddcx.PFN_IDDCXSWAPCHAINRELEASEANDACQUIREBUFFER2
tech.root: display
title: PFN_IDDCXSWAPCHAINRELEASEANDACQUIREBUFFER2
ms.date: 02/10/2025
targetos: Windows
description: Learn more about the PFN_IDDCXSWAPCHAINRELEASEANDACQUIREBUFFER2 function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2 September Update (IddCx version 1.10)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - iddcx.h
api_name:
 - PFN_IDDCXSWAPCHAINRELEASEANDACQUIREBUFFER2
f1_keywords:
 - PFN_IDDCXSWAPCHAINRELEASEANDACQUIREBUFFER2
 - iddcx/PFN_IDDCXSWAPCHAINRELEASEANDACQUIREBUFFER2
dev_langs:
 - c++
helpviewer_keywords:
 - PFN_IDDCXSWAPCHAINRELEASEANDACQUIREBUFFER2
---

## -description

**PFN_IDDCXSWAPCHAINRELEASEANDACQUIREBUFFER2** is a pointer to an OS callback function that releases the buffer from the swap chain and acquires a new buffer.

## -parameters

### -param DriverGlobals

[in] Contains system-defined per-driver data.

### -param SwapChainObject

[in] The swap chain object that the buffer is associated with.

### -param pInArgs

[in] Input arguments for the function.

### -param pOutArgs

[out] Output arguments for the function.

## -returns

**PFN_IDDCXSWAPCHAINRELEASEANDACQUIREBUFFER2** returns an NTSTATUS value that indicates the success or failure of the function.

## -remarks

An indirect display driver (IDD) shouldn't use this function pointer to directly. IDDs should instead call [**IddCxSwapChainReleaseAndAcquireBuffer2**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer2.md).

## -see-also

[**IddCxSwapChainReleaseAndAcquireBuffer2**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer2.md)
