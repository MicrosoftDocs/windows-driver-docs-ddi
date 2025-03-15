---
UID: NS:d3dkmdt._D3DKMT_DRIVERCAPS_EXT
tech.root: display
title: D3DKMT_DRIVERCAPS_EXT
ms.date: 01/21/2025
targetos: Windows
description: Learn more about the D3DKMT_DRIVERCAPS_EXT structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmdt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10 (WDDM 2.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DKMT_DRIVERCAPS_EXT
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _D3DKMT_DRIVERCAPS_EXT
 - D3DKMT_DRIVERCAPS_EXT
f1_keywords:
 - _D3DKMT_DRIVERCAPS_EXT
 - d3dkmdt/_D3DKMT_DRIVERCAPS_EXT
 - D3DKMT_DRIVERCAPS_EXT
 - d3dkmdt/D3DKMT_DRIVERCAPS_EXT
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DKMT_DRIVERCAPS_EXT
---

## -description

The **D3DKMT_DRIVERCAPS_EXT** structure describes the extended capabilities of the display miniport driver (KMD).

## -struct-fields

### -field VirtualModeSupport

The driver supports virtual mode.

### -field Usb4MonitorSupport

The driver supports monitors connected via USB4.

### -field Reserved

Reserved for future use.

### -field Value

An alternative way to access the capability bits.

## -see-also

[**D3DKMTQueryAdapterInfo**](../d3dkmthk/nf-d3dkmthk-d3dkmtqueryadapterinfo.md)
