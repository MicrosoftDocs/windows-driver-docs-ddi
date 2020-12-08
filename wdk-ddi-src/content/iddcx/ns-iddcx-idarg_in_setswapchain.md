---
UID: NS:iddcx.IDARG_IN_SETSWAPCHAIN
title: IDARG_IN_SETSWAPCHAIN (iddcx.h)
description: The IDARG_IN_SETSWAPCHAIN structure provides information used to set the indirect swapchain.
old-location: display\idarg_in_setswapchain.htm
tech.root: display
ms.date: 09/24/2020
keywords: ["IDARG_IN_SETSWAPCHAIN structure"]
ms.keywords: IDARG_IN_SETSWAPCHAIN, IDARG_IN_SETSWAPCHAIN structure [Display Devices], display.idarg_in_setswapchain, iddcx/IDARG_IN_SETSWAPCHAIN
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IDARG_IN_SETSWAPCHAIN
 - iddcx/IDARG_IN_SETSWAPCHAIN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_IN_SETSWAPCHAIN
---

# IDARG_IN_SETSWAPCHAIN structure

## -description

The **IDARG_IN_SETSWAPCHAIN** structure provides information used to set the indirect swapchain.

## -struct-fields

### -field hSwapChain

[in] Handle to an opaque, OS-created IDDCX_SWAPCHAIN object that will be used to pass the desktop image to the driver for processing, transmission and display.

### -field hNextSurfaceAvailable

[in] Handle to the auto reset event that is signaled when the new image to encode is ready.

### -field RenderAdapterLuid

[In] LUID of the adapter where the desktop image was rendered.

## -see-also

[**EVT_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN**](nc-iddcx-evt_idd_cx_monitor_assign_swapchain.md)
