---
UID: NS:d3dkmthk._D3DKMT_GET_DEVICE_VIDPN_OWNERSHIP_INFO
title: D3DKMT_GET_DEVICE_VIDPN_OWNERSHIP_INFO (d3dkmthk.h)
description: Learn more about the D3DKMT_GET_DEVICE_VIDPN_OWNERSHIP_INFO structure.
ms.date: 02/06/2025
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1703 (WDDM 2.2)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DKMT_GET_DEVICE_VIDPN_OWNERSHIP_INFO
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_GET_DEVICE_VIDPN_OWNERSHIP_INFO
 - d3dkmthk/_D3DKMT_GET_DEVICE_VIDPN_OWNERSHIP_INFO
 - D3DKMT_GET_DEVICE_VIDPN_OWNERSHIP_INFO
 - d3dkmthk/D3DKMT_GET_DEVICE_VIDPN_OWNERSHIP_INFO
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_GET_DEVICE_VIDPN_OWNERSHIP_INFO
 - D3DKMT_GET_DEVICE_VIDPN_OWNERSHIP_INFO
dev_langs:
 - c++
---

# D3DKMT_GET_DEVICE_VIDPN_OWNERSHIP_INFO structure

## -description

The **D3DKMT_GET_DEVICE_VIDPN_OWNERSHIP_INFO** structure is used to get device VidPn ownership information.

## -struct-fields

### -field hDevice

A handle to the device.

### -field bFailedDwmAcquireVidPn

Boolean value that indicates whether the Desktop Windows Manager (DWM) failed to acquire the VidPn. This is set TRUE if DWM failed to acquire the VidPn due to another DWM device already owning the VidPn.

## -see-also

[**D3DKMTQueryAdapterInfo**](nf-d3dkmthk-d3dkmtqueryadapterinfo.md)
