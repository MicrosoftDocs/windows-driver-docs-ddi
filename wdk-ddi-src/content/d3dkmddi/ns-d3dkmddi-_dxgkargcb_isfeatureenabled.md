---
UID: NS:d3dkmddi._DXGKARGCB_ISFEATUREENABLED
title: _DXGKARGCB_ISFEATUREENABLED
author: windows-driver-content
description: Arguments used to query the driver feature is enabled.
tech.root: display
ms.assetid: ebef9742-03ea-4402-a62e-9f45f11230cd
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: struct
f1_keywords:
 - "d3dkmddi/_DXGKARGCB_ISFEATUREENABLED"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARGCB_ISFEATUREENABLED, DXGKARGCB_ISFEATUREENABLED, *INOUT_PDXGKARGCB_ISFEATUREENABLED
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGKARGCB_ISFEATUREENABLED
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3dkmddi.h
api_name: 
 - _DXGKARGCB_ISFEATUREENABLED
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: DXGKDDI_INTERFACE_VERSION_WDDM2_6, 19H1
---

# _DXGKARGCB_ISFEATUREENABLED structure

## -description

Arguments used to query the driver feature's enabled state.

## -struct-fields

### -field DeviceHandle
 
[in] Device handle that was passed to the driver [DxgkDdiStartDevice](../dispmprt/nc-dispmprt-dxgkddi_start_device.md) function.

### -field FeatureId

[in] Feature ID to query enabled state for.

### -field Enabled
 
[out] FALSE if the OS instructs the driver not to enable the feature. TRUE if the OS allows the driver to enable the feature.

## -remarks

## -see-also
