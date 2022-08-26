---
UID: NS:d3dkmddi._DXGKARG_QUERYCONNECTIONCHANGE
title: DXGKARG_QUERYCONNECTIONCHANGE (d3dkmddi.h)
description: Used to hold the arguments for DXGKDDI_QUERYCONNECTIONCHANGE.
old-location: display\dxgkarg_queryconnectionchange.htm
ms.date: 08/24/2022
keywords: ["DXGKARG_QUERYCONNECTIONCHANGE structure"]
ms.keywords: "*IN_PDXGKARG_QUERYCONNECTIONCHANGE, DXGKARG_QUERYCONNECTIONCHANGE, DXGKARG_QUERYCONNECTIONCHANGE structure [Display Devices], _DXGKARG_QUERYCONNECTIONCHANGE, d3dkmddi/DXGKARG_QUERYCONNECTIONCHANGE, display.dxgkarg_queryconnectionchange"
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
tech.root: display
req.typenames: DXGKARG_QUERYCONNECTIONCHANGE
f1_keywords:
 - _DXGKARG_QUERYCONNECTIONCHANGE
 - d3dkmddi/_DXGKARG_QUERYCONNECTIONCHANGE
 - DXGKARG_QUERYCONNECTIONCHANGE
 - d3dkmddi/DXGKARG_QUERYCONNECTIONCHANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_QUERYCONNECTIONCHANGE
 - DXGKARG_QUERYCONNECTIONCHANGE
---

# DXGKARG_QUERYCONNECTIONCHANGE structure

## -description

A **DXGKARG_QUERYCONNECTIONCHANGE** structure holds the arguments for [**DXGKDDI_QUERYCONNECTIONCHANGE**](nc-d3dkmddi-dxgkddi_queryconnectionchange.md).

## -struct-fields

### -field ConnectionChange

[out] A [**DXGK_CONNECTION_CHANGE**](ns-d3dkmddi-_dxgk_connection_change.md) structure into which the driver copies the oldest available connection change.

### -field Usb4MonitorInfo

[out] An OS-allocated [**DXGK_CONNECTION_USB4_INFO**](ns-d3dkmddi-dxgk_connection_usb4_info.md) structure that the driver should complete if [**MonitorConnectFlags.Usb4DisplayPortMonitor**](ns-d3dkmddi-dxgk_connection_monitor_connect_flags.md) was set. Available starting in Windows 11 (WDDM 3.0).

## -see-also

[**DXGKDDI_QUERYCONNECTIONCHANGE**](nc-d3dkmddi-dxgkddi_queryconnectionchange.md)
