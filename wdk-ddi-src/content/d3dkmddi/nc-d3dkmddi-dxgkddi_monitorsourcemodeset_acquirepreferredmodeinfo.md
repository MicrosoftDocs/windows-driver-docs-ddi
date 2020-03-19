---
UID: NC:d3dkmddi.DXGKDDI_MONITORSOURCEMODESET_ACQUIREPREFERREDMODEINFO
title: DXGKDDI_MONITORSOURCEMODESET_ACQUIREPREFERREDMODEINFO (d3dkmddi.h)
description: The pfnAcquirePreferredModeInfo returns a descriptor of the preferred mode in a specified monitor source mode set object.
old-location: display\dxgk_monitorsourcemodeset_interface_pfnacquirepreferredmodeinfo.htm
ms.assetid: 80d3d199-42ad-4f21-8122-05dfad37016d
ms.date: 05/10/2018
keywords: ["DXGKDDI_MONITORSOURCEMODESET_ACQUIREPREFERREDMODEINFO callback function"]
ms.keywords: DXGKDDI_MONITORSOURCEMODESET_ACQUIREPREFERREDMODEINFO, DXGKDDI_MONITORSOURCEMODESET_ACQUIREPREFERREDMODEINFO callback, VidPnFunctions_c7c55840-18b7-40ad-8cf9-5350c7723246.xml, d3dkmddi/pfnAcquirePreferredModeInfo, display.dxgk_monitorsourcemodeset_interface_pfnacquirepreferredmodeinfo, pfnAcquirePreferredModeInfo, pfnAcquirePreferredModeInfo callback function [Display Devices]
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/pfnAcquirePreferredModeInfo"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnAcquirePreferredModeInfo
product:
 - Windows
---

# DXGKDDI_MONITORSOURCEMODESET_ACQUIREPREFERREDMODEINFO callback function

## -description

The <b>pfnAcquirePreferredModeInfo</b> returns a descriptor of the preferred mode in a specified monitor source mode set object.

## -parameters

### -param hMonitorSourceModeSet

[in] A handle to a monitor source mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset">pfnAcquireMonitorSourceModeSet</a> function of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Monitor interface</a>.

### -param ppFirstMonitorSourceModeInfo

[out] A pointer to a variable that receives a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_monitor_source_mode">D3DKMDT_MONITOR_SOURCE_MODE</a> structure. The structure contains a variety of information about the preferred monitor source mode, including its ID and video signal.

## -returns

The <b>pfnAcquirePreferredModeInfo</b> function returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function successfully returned a descriptor of the preferred mode.|
|STATIS_GRAPHICS_NO_PREFERRED_MODE|The function succeeded, but the specified monitor source mode set does not have a preferred mode.|
|STATUS_GRAPHICS_INVALID_MONITOR_SOURCEMODESET|The handle supplied in hMonitorSourceModeSet was invalid.|

## -remarks

When you have finished using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_monitor_source_mode">D3DKMDT_MONITOR_SOURCE_MODE</a> structure, you must release the structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorsourcemodeset_releasemodeinfo">pfnReleaseModeInfo</a>.

The D3DKMDT_HMONITORSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>.

