---
UID: NE:iddcx.IDDCX_DEVICE_FEATURES_1_11
title: IDDCX_DEVICE_FEATURES_1_11 (iddcx.h)
description: Enum used to indicate how a given supported feature is implemented.
prerelease: true
old-location:
tech.root: display
ms.date: 02/17/2026
keywords: ["IDDCX_DEVICE_FEATURES_1_11 enumeration"]
ms.keywords: DDCX_DEVICE_FEATURES_1_11, IDDCX_DEVICE_FEATURES_1_11 enumeration [Display Devices], IDDCX_DEVICE_FEATURES_1_11_D3D12, IDDCX_DEVICE_FEATURES_1_11_DISPLAY_ID_ONLY, IDDCX_DEVICE_FEATURES_1_11_UPDATE_REENCODE_COUNT, iddcx/DDCX_DEVICE_FEATURES_1_11, iddcx/IDDCX_DEVICE_FEATURES_1_11_D3D12, iddcx/IDDCX_DEVICE_FEATURES_1_11_DISPLAY_ID_ONLY, iddcx/IDDCX_DEVICE_FEATURES_1_11_UPDATE_REENCODE_COUNT
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
 - IDDCX_DEVICE_FEATURES_1_11
 - iddcx/IDDCX_DEVICE_FEATURES_1_11
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_DEVICE_FEATURES_1_11
---

# IDDCX_DEVICE_FEATURES_1_11 enumeration

## -description

A **IDDCX_FEATURE_IMPLEMENTATION** value is used to indicate how a given IddCx version 1.11 supported feature is implemented.

## -enum-fields

### -field IDDCX_DEVICE_FEATURES_1_11_D3D12:1

The underlying OS supports D3D12 swap chains.

### -field IDDCX_DEVICE_FEATURES_1_11_DISPLAY_ID_ONLY:2

The underlying OS supports the driver submitting DisplayID only monitor descriptors.

### -field IDDCX_DEVICE_FEATURES_1_11_UPDATE_REENCODE_COUNT:4

The underlying OS supports updating the StaticDesktopReencodeFrameCount value for a swap chain.

## -see-also

[**IDARG_OUT_FEATURES_SUPPORTED**](ns-iddcx-idarg_out_features_supported.md)
