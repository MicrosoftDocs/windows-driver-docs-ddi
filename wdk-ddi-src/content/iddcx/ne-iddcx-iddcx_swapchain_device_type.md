---
UID: NE:iddcx.IDDCX_SWAPCHAIN_DEVICE_TYPE
title: IDDCX_SWAPCHAIN_DEVICE_TYPE (iddcx.h)
description: Enum used to indicate how to set the swap chain device type.
prerelease: true
old-location:
tech.root: display
ms.date: 02/17/2026
keywords: ["IDDCX_SWAPCHAIN_DEVICE_TYPE enumeration"]
ms.keywords: IDDCX_SWAPCHAIN_DEVICE_TYPE, IDDCX_SWAPCHAIN_DEVICE_TYPE enumeration [Display Devices], IDDCX_SWAPCHAIN_DEVICE_TYPE_INVALID, IDDCX_SWAPCHAIN_DEVICE_TYPE_DXGI, IDDCX_SWAPCHAIN_DEVICE_TYPE_D3D12, iddcx/IDDCX_SWAPCHAIN_DEVICE_TYPE, iddcx/IDDCX_SWAPCHAIN_DEVICE_TYPE_INVALID, iddcx/IDDCX_SWAPCHAIN_DEVICE_TYPE_DXGI, iddcx/IDDCX_SWAPCHAIN_DEVICE_TYPE_D3D12
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
 - IDDCX_SWAPCHAIN_DEVICE_TYPE
 - iddcx/IDDCX_SWAPCHAIN_DEVICE_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_SWAPCHAIN_DEVICE_TYPE
---

# IDDCX_SWAPCHAIN_DEVICE_TYPE enumeration

## -description

A **IDDCX_SWAPCHAIN_DEVICE_TYPE** value is used to indicate how to set the swap chain device type.

## -enum-fields

### -field IDDCX_SWAPCHAIN_DEVICE_TYPE_INVALID:0

The swap chain device type is invalid.

### -field IDDCX_SWAPCHAIN_DEVICE_TYPE_DXGI:1

The value used when the driver wants to set **[IDARG_IN_SWAPCHAINSETDEVICE2](ns-iddcx-idarg_in_swapchainsetdevice2.md)::Driver.pDxgiDevice**.

### -field IDDCX_SWAPCHAIN_DEVICE_TYPE_D3D12:2

The value used when the driver wants to set **IDARG_IN_SWAPCHAINSETDEVICE2::Driver.pD3d12Device**.

## -see-also

[**IDARG_IN_SWAPCHAINSETDEVICE2**](ns-iddcx-idarg_in_swapchainsetdevice2.md)
