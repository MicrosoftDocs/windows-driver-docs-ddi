---
UID: NF:iddcx.IddCxSwapChainReleaseAndAcquireSystemBuffer
title: IddCxSwapChainReleaseAndAcquireSystemBuffer
ms.date: 10/20/2020
ms.assetid: 21034f7b-ba2a-44d3-89c6-1e2162dc1771
tech.root: display
ms.topic: language-reference
targetos: Windows
description: IddCxSwapChainReleaseAndAcquireSystemBuffer releases and acquires buffers from the swapchain.
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
req.target-min-winverclnt: Windows 10, version 20H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - iddcx.h
api_name:
 - IddCxSwapChainReleaseAndAcquireSystemBuffer
f1_keywords:
 - IddCxSwapChainReleaseAndAcquireSystemBuffer
 - iddcx/IddCxSwapChainReleaseAndAcquireSystemBuffer
dev_langs:
 - c++
---

## -description

**IddCxSwapChainReleaseAndAcquireSystemBuffer** releases and acquires buffers from the swapchain.

## -parameters

### -param SwapChainObject

[in] The [IDDCX_SWAPCHAIN](/windows-hardware/drivers/display/iddcx-objects) object used for querying the physical address of the currently acquired surface.

### -param pOutArgs

[out] Pointer to a [**IDARG_OUT_RELEASEANDACQUIRESYSTEMBUFFER**](ns-iddcx-idarg_out_releaseandacquiresystembuffer.md) structure in which the resulting information from the release and acquire operation is returned.

## -returns

**IddCxSwapChainReleaseAndAcquireSystemBuffer** returns S_OK on success; otherwise it returns an appropriate error code.

## -remarks

In addition to releasing and acquiring buffers from the swapchain, **IddCxSwapChainReleaseAndAcquireSystemBuffer** also unmaps and unlocks the buffer being released while mapping and locking the buffer being acquired. For this reason, it is not valid to call [**IddCxSwapChainReleaseAndAcquireBuffer**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer.md) subsequent to calling this method. The [**IDDCX_SYSTEM_BUFFER_INFO**](ns-iddcx-iddcx_system_buffer_info.md) structure pointed to by **pBufferInfo** is filled with valid information only on a successful release and acquire as indicated by a return value of S_OK.

## -see-also

[**IDARG_OUT_RELEASEANDACQUIRESYSTEMBUFFER**](ns-iddcx-idarg_out_releaseandacquiresystembuffer.md)

[**IDDCX_SYSTEM_BUFFER_INFO**](ns-iddcx-iddcx_system_buffer_info.md)

[**IddCxSwapChainReleaseAndAcquireBuffer**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer.md)
