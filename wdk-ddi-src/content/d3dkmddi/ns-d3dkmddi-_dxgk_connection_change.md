---
UID: NS:d3dkmddi._DXGK_CONNECTION_CHANGE
title: DXGK_CONNECTION_CHANGE (d3dkmddi.h)
description: Structure to describe the most recently updated status of the link for a target.
old-location: display\dxgk_connection_change.htm
ms.date: 08/24/2022
keywords: ["DXGK_CONNECTION_CHANGE structure"]
ms.keywords: "*PDXGK_CONNECTION_CHANGE, DXGK_CONNECTION_CHANGE, DXGK_CONNECTION_CHANGE structure [Display Devices], PDXGK_CONNECTION_CHANGE, PDXGK_CONNECTION_CHANGE structure pointer [Display Devices], _DXGK_CONNECTION_CHANGE, d3dkmddi/DXGK_CONNECTION_CHANGE, d3dkmddi/PDXGK_CONNECTION_CHANGE, display.dxgk_connection_change"
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
req.typenames: DXGK_CONNECTION_CHANGE, *PDXGK_CONNECTION_CHANGE
f1_keywords:
 - _DXGK_CONNECTION_CHANGE
 - d3dkmddi/_DXGK_CONNECTION_CHANGE
 - PDXGK_CONNECTION_CHANGE
 - d3dkmddi/PDXGK_CONNECTION_CHANGE
 - DXGK_CONNECTION_CHANGE
 - d3dkmddi/DXGK_CONNECTION_CHANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_CONNECTION_CHANGE
 - PDXGK_CONNECTION_CHANGE
 - DXGK_CONNECTION_CHANGE
---

# DXGK_CONNECTION_CHANGE structure

## -description

**DXGK_CONNECTION_CHANGE** describes the most recently updated status of the link for a target.

## -struct-fields

### -field ConnectionChangeId

The per target unique ID for the transition being reported. This value must be unique across all targets on the adapter and must be monotonically increasing for each change reported.

### -field TargetId

The target ID for which the change is being reported. This target ID must have been reported to the OS before and must be in a state that supports the given change.

### -field ConnectionStatus

A [**DXGK_CONNECTION_STATUS**](ne-d3dkmddi-_dxgk_connection_status.md) value that specifies the status of the connection.

### -field Reserved

Reserved for system use.

### -field MonitorConnect

Describes the monitor that has been connected.

### -field MonitorConnect.LinkTargetType

A [**D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY**](../d3dkmdt/ne-d3dkmdt-_d3dkmdt_video_output_technology.md) value that identifies the video output technology of the monitor that has been connected. The **D3DKMDT_VOT_INTERNAL** and **D3DKMDT_VOT_MIRACAST** values are not allowed.

### -field MonitorConnect.MonitorConnectFlags

A [**DXGK_CONNECTION_MONITOR_CONNECT_FLAGS**](ns-d3dkmddi-dxgk_connection_monitor_connect_flags.md) structure with flags for the connected monitor.

### -field TargetConnect

Describes the current target's connector.

#### TargetConnect.BaseTargetType

A [**D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY**](../d3dkmdt/ne-d3dkmdt-_d3dkmdt_video_output_technology.md) value that identifies the video output technology of the current target's connector. As with **MonitorConnect.LinkTargetType**, the **D3DKMDT_VOT_INTERNAL** and **D3DKMDT_VOT_MIRACAST** values are not allowed.

#### TargetConnect.NewTargetId

The target ID for which the change is being reported. This target ID must have been reported to the OS before and must be in a state which supports the given change.

### -field TargetJoin

Describes the joining target's connector.

#### TargetJoin.BaseTargetType

This is the video output technology of the connector of the new target. As with **MonitorConnect.LinkTargetType**, the **D3DKMDT_VOT_INTERNAL** and **D3DKMDT_VOT_MIRACAST** values are not allowed.  

> [!NOTE]
> The same **BaseTargetType** must be reported for all targets that are being joined to each other.

#### TargetJoin.NewTargetId

The target ID for which the change is being reported. This target ID must have been reported to the OS before and must be in a state which supports the given change.

## -see-also

[**D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY**](../d3dkmdt/ne-d3dkmdt-_d3dkmdt_video_output_technology.md)

[**DXGKARG_QUERYCONNECTIONCHANGE**](ns-d3dkmddi-_dxgkarg_queryconnectionchange.md)
