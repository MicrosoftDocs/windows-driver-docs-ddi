---
UID: NS:d3dkmddi._DXGK_CONNECTION_MONITOR_CONNECT_FLAGS
tech.root: display
title: DXGK_CONNECTION_MONITOR_CONNECT_FLAGS
ms.date: 08/24/2022
targetos: Windows
description: Learn more about the DXGK_CONNECTION_MONITOR_CONNECT_FLAGS structure.
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
req.typenames: DXGK_CONNECTION_MONITOR_CONNECT_FLAGS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_CONNECTION_MONITOR_CONNECT_FLAGS
 - DXGK_CONNECTION_MONITOR_CONNECT_FLAGS
f1_keywords:
 - _DXGK_CONNECTION_MONITOR_CONNECT_FLAGS
 - d3dkmddi/_DXGK_CONNECTION_MONITOR_CONNECT_FLAGS
 - DXGK_CONNECTION_MONITOR_CONNECT_FLAGS
 - d3dkmddi/DXGK_CONNECTION_MONITOR_CONNECT_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_CONNECTION_MONITOR_CONNECT_FLAGS
---

## -description

The **DXGK_CONNECTION_MONITOR_CONNECT_FLAGS** structure specifies flags for the connected monitor.

## -struct-fields

### -field Usb4DisplayPortMonitor

The monitor is a USB4 connected monitor.

### -field Reserved

Reserved; do not use.

### -field Value

Can be used to access the above bit fields.

## -remarks

## -see-also

[**DXGK_CONNECTION_CHANGE**]( ns-d3dkmddi-_dxgk_connection_change.md)

[**DXGKDDI_QUERYCONNECTIONCHANGE**](nc-d3dkmddi-dxgkddi_queryconnectionchange.md)
