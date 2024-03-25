---
UID: NS:d3dkmddi._DXGK_CONNECTION_USB4_INFO
tech.root: display
title: DXGK_CONNECTION_USB4_INFO
ms.date: 08/26/2022
targetos: Windows
description: Learn more about the DXGK_CONNECTION_USB4_INFO structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_CONNECTION_USB4_INFO, *PDXGK_CONNECTION_USB4_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_CONNECTION_USB4_INFO
 - PDXGK_CONNECTION_USB4_INFO
 - DXGK_CONNECTION_USB4_INFO
f1_keywords:
 - _DXGK_CONNECTION_USB4_INFO
 - d3dkmddi/_DXGK_CONNECTION_USB4_INFO
 - PDXGK_CONNECTION_USB4_INFO
 - d3dkmddi/PDXGK_CONNECTION_USB4_INFO
 - DXGK_CONNECTION_USB4_INFO
 - d3dkmddi/DXGK_CONNECTION_USB4_INFO
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_CONNECTION_USB4_INFO
---

## -description

A driver that supports USB4 returns information in a **DXGK_CONNECTION_USB4_INFO** structure when a new monitor connected over USB4 arrives.

## -struct-fields

### -field Dpcd_DP_IN_Adapter_Number

Uniquely identifies the DisplayPort-IN adapter on the USB4 device.

### -field Dpcd_USB4_Driver_ID

Uniquely identifies the host router in the system.

### -field Dpcd_USB4_ROUTER_TOPOLOGY_ID[5]

Uniquely identifies the USB4 device in the host router domain.

## -remarks

See [Supporting DisplayPort monitors over USB4 in KMD](/windows-hardware/drivers/display/supporting-usb4) for more information.

## -see-also

[**DXGKARG_QUERYCONNECTIONCHANGE**](ns-d3dkmddi-_dxgkarg_queryconnectionchange.md)
