---
UID: NS:iddcx.IDARG_IN_SWAPCHAINSETDEVICE2
title: IDARG_IN_SWAPCHAINSETDEVICE2 (iddcx.h)
description: Gives more information about the device that will process the swap chain.
prerelease: true
old-location: 
tech.root: display
ms.date: 02/17/2026
keywords: ["IDARG_IN_SWAPCHAINSETDEVICEs structure"]
ms.keywords: IDARG_IN_SWAPCHAINSETDEVICEs, IDARG_IN_SWAPCHAINSETDEVICEs structure [Display Devices], iddcx/IDARG_IN_SWAPCHAINSETDEVICE2
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 11, 26H1 (IddCx 1.11)
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
 - IDARG_IN_SWAPCHAINSETDEVICE2
 - iddcx/IDARG_IN_SWAPCHAINSETDEVICE2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_IN_SWAPCHAINSETDEVICE2
---

# IDARG_IN_SWAPCHAINSETDEVICE2 structure

## -description

Gives more information about the device that will process the swap chain.

## -struct-fields

### -field Type

This must be set correctly by the driver so the OS knows how to access the **IDARG_IN_SWAPCHAINSETDEVICE2::Device** object.

### -field pDxgiDevice

Must be set when **IDARG_IN_SWAPCHAINSETDEVICE2::Type** is set to IDDCX_SWAPCHAIN_DEVICE_TYPE_DXGI.

### -field pD3d12Device

Must be set when **IDARG_IN_SWAPCHAINSETDEVICE2::Type** is set to IDDCX_SWAPCHAIN_DEVICE_TYPE_D3D12.

## -see-also

[IDDCX_SWAPCHAIN_DEVICE_TYPE](ne-iddcx-iddcx_swapchain_device_type.md)
