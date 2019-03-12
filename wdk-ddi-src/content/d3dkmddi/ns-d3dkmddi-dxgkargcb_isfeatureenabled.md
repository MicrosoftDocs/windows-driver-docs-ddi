---
UID: NS:d3dkmddi._DXGKARGCB_ISFEATUREENABLED
title: DXGKARGCB_ISFEATUREENABLED
author: windows-driver-content
description: Arguments used to determine the enabled state of a particular driver feature.
tech.root: display
ms.assetid: 6181995e-2a67-4bc8-8fcd-45adcf9e4b42
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: struct
ms.keywords: DXGKARGCB_ISFEATUREENABLED, DXGKARGCB_ISFEATUREENABLED, *INOUT_PDXGKARGCB_ISFEATUREENABLED
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
 - DXGKARGCB_ISFEATUREENABLED
product:
- Windows
targetos: Windows
ms.custom: DXGKDDI_INTERFACE_VERSION_WDDM2_6
---

# DXGKARGCB_ISFEATUREENABLED structure

## -description

Arguments used to determine the enabled state of a particular driver feature.

## -struct-fields

### -field DeviceHandle

[in] Device handle that was passed to the driver [DxgkDdiStartDevice](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_start_device) function.

### -field FeatureId

[in] The feature ID to query the enabled state for.

### -field Enabled
 
[out] FALSE if the OS instructs the driver not to enable the feature. TRUE if the OS allows the driver to enable the feature.

## -remarks

## -see-also