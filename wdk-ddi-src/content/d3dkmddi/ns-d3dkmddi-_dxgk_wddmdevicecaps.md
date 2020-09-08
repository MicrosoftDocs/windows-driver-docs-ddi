---
UID: NS:d3dkmddi._DXGK_WDDMDEVICECAPS
title: _DXGK_WDDMDEVICECAPS
author: windows-driver-content
description: Contains the WDDM capabilities that was returned from the KMD in response to the DxgkDdiQueryAdapterInfo request for a DXGK_QUERYADAPTERINFOTYPE value of type DXGKQAITYPE_WDDMDEVICECAPS.
tech.root: display
ms.assetid: 416f3f32-7bca-4ffa-893b-5d7d5916a381
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["DXGK_WDDMDEVICECAPS structure"]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGK_WDDMDEVICECAPS, DXGK_WDDMDEVICECAPS,
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
req.typenames: DXGK_WDDMDEVICECAPS
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _DXGK_WDDMDEVICECAPS
 - d3dkmddi/_DXGK_WDDMDEVICECAPS
 - DXGK_WDDMDEVICECAPS
 - d3dkmddi/DXGK_WDDMDEVICECAPS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_WDDMDEVICECAPS
product:
 - Windows
dev_langs:
 - c++
---

# _DXGK_WDDMDEVICECAPS structure


## -description

Contains the WDDM capabilities that was returned from the KMD, in response to the [DxgkDdiQueryAdapterInfo](../d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo.md) request for a [DXGK_QUERYADAPTERINFOTYPE](../d3dkmddi/ne-d3dkmddi-_dxgk_queryadapterinfotype.md) value of type **DXGKQAITYPE_WDDMDEVICECAPS**.

These capabilities are queried by the OS during device initialization after [DxgkDdiAddDevice](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) returns, and before [DxgkDdiStartDevice](../dispmprt/nc-dispmprt-dxgkddi_start_device.md) is called.

## -struct-fields

### -field WDDMVersion

 
The capabilities of a display miniport driver that the driver provides through a call to its DxgkDdiQueryAdapterInfo function. This value is the same as the **WDDMVersion** value in [DXGK_DRIVERCAPS](../d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps.md) structure.

## -remarks

## -see-also

