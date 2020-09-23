---
UID: NC:d3dkmddi.DXGKDDI_MONITORSOURCEMODESET_GETNUMMODES
title: DXGKDDI_MONITORSOURCEMODESET_GETNUMMODES (d3dkmddi.h)
description: The pfnGetNumModes function returns the number modes in a specified monitor source mode set.
old-location: display\dxgk_monitorsourcemodeset_interface_pfngetnummodes.htm
ms.assetid: 58daf5be-45c5-493b-9d51-ef48bb123dce
ms.date: 05/10/2018
keywords: ["DXGKDDI_MONITORSOURCEMODESET_GETNUMMODES callback function"]
ms.keywords: DXGKDDI_MONITORSOURCEMODESET_GETNUMMODES, DXGKDDI_MONITORSOURCEMODESET_GETNUMMODES callback, VidPnFunctions_ac29494d-c35e-46bb-bfc1-6aaf70edbc2d.xml, d3dkmddi/pfnGetNumModes, display.dxgk_monitorsourcemodeset_interface_pfngetnummodes, pfnGetNumModes, pfnGetNumModes callback function [Display Devices]
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
 - DXGKDDI_MONITORSOURCEMODESET_GETNUMMODES
 - d3dkmddi/DXGKDDI_MONITORSOURCEMODESET_GETNUMMODES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnGetNumModes
product:
 - Windows
---

# DXGKDDI_MONITORSOURCEMODESET_GETNUMMODES callback function


## -description

The <b>pfnGetNumModes</b> function returns the number modes in a specified monitor source mode set.

## -parameters

### -param hMonitorSourceModeSet

A handle to a monitor source mode set object. The display miniport driver previously obtained this handle by calling the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset">pfnAcquireMonitorSourceModeSet</a> function of the <a href="/windows-hardware/drivers/ddi/index">Monitor interface</a>.

### -param pNumMonitorSourceModes

A pointer to a SIZE_T-typed variable that receives the number of monitor source modes in the set.

## -returns

The <b>pfnGetNumModes</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_MONITOR_SOURCEMODESET|The handle supplied in hMonitorSourceModeSet was invalid.|

## -remarks

The D3DKMDT_HMONITORSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorsourcemodeset_acquirefirstmodeinfo">pfnAcquireFirstModeInfo</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorsourcemodeset_acquirenextmodeinfo">pfnAcquireNextModeInfo</a>