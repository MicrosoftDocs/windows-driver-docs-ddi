---
UID: NC:d3dkmddi.DXGKDDI_MONITORSOURCEMODESET_ACQUIREFIRSTMODEINFO
title: DXGKDDI_MONITORSOURCEMODESET_ACQUIREFIRSTMODEINFO (d3dkmddi.h)
description: The pfnAcquireFirstModeInfo function returns a descriptor of the first mode in a specified monitor source mode set.
old-location: display\dxgk_monitorsourcemodeset_interface_pfnacquirefirstmodeinfo.htm
ms.assetid: d448c3f4-7adb-4ceb-8c42-8cba3d2cfeae
ms.date: 05/10/2018
ms.keywords: DXGKDDI_MONITORSOURCEMODESET_ACQUIREFIRSTMODEINFO, DXGKDDI_MONITORSOURCEMODESET_ACQUIREFIRSTMODEINFO callback, VidPnFunctions_81493c6c-3b78-4c4b-969c-276a459a198d.xml, d3dkmddi/pfnAcquireFirstModeInfo, display.dxgk_monitorsourcemodeset_interface_pfnacquirefirstmodeinfo, pfnAcquireFirstModeInfo, pfnAcquireFirstModeInfo callback function [Display Devices]
ms.topic: callback
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
 - "d3dkmddi/pfnAcquireFirstModeInfo"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnAcquireFirstModeInfo
product:
 - Windows
---

# DXGKDDI_MONITORSOURCEMODESET_ACQUIREFIRSTMODEINFO callback function

## -description

The <b>pfnAcquireFirstModeInfo</b> function returns a descriptor of the first mode in a specified monitor source mode set.

## -parameters

### -param hMonitorSourceModeSet

[in] A handle to a monitor source mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset">pfnAcquireMonitorSourceModeSet</a> function of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Monitor interface</a>.

### -param ppFirstMonitorSourceModeInfo

[out] A pointer to a variable that receives a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_monitor_source_mode">D3DKMDT_MONITOR_SOURCE_MODE</a> structure. The structure contains a variety of information about the monitor source mode, including its ID and video signal characteristics.

## -returns

The <b>pfnAcquireFirstModeInfo</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_MONITOR_SOURCEMODESET|The handle supplied in hMonitorSourceModeSet was invalid.|

## -remarks

When you have finished using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_monitor_source_mode">D3DKMDT_MONITOR_SOURCE_MODE</a> structure, you must release the structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorsourcemodeset_releasemodeinfo">pfnReleaseModeInfo</a>.

You can enumerate all the modes that belong to a VidPN monitor source mode set object by calling <b>pfnAcquireFirstModeInfo</b> and then making a sequence of calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorsourcemodeset_acquirenextmodeinfo">pfnAcquireNextModeInfo</a>.

The D3DKMDT_HMONITORSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_monitor_source_mode">D3DKMDT_MONITOR_SOURCE_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorsourcemodeset_acquirenextmodeinfo">pfnAcquireNextModeInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorsourcemodeset_releasemodeinfo">pfnReleaseModeInfo</a>

