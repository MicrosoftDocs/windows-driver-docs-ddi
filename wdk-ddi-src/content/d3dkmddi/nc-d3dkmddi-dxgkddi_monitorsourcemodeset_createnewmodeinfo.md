---
UID: NC:d3dkmddi.DXGKDDI_MONITORSOURCEMODESET_CREATENEWMODEINFO
title: DXGKDDI_MONITORSOURCEMODESET_CREATENEWMODEINFO (d3dkmddi.h)
description: The pfnCreateNewModeInfo function returns a pointer to a D3DKMDT_MONITOR_SOURCE_MODE structure that the display miniport driver populates before calling pfnAddMode.
old-location: display\dxgk_monitorsourcemodeset_interface_pfncreatenewmodeinfo.htm
ms.assetid: 314b345c-a40b-418d-a2d8-c7b42e5fd27d
ms.date: 05/10/2018
keywords: ["DXGKDDI_MONITORSOURCEMODESET_CREATENEWMODEINFO callback function"]
ms.keywords: DXGKDDI_MONITORSOURCEMODESET_CREATENEWMODEINFO, DXGKDDI_MONITORSOURCEMODESET_CREATENEWMODEINFO callback, VidPnFunctions_4b8b1581-4518-471d-a79e-ed05899ad500.xml, d3dkmddi/pfnCreateNewModeInfo, display.dxgk_monitorsourcemodeset_interface_pfncreatenewmodeinfo, pfnCreateNewModeInfo, pfnCreateNewModeInfo callback function [Display Devices]
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
 - DXGKDDI_MONITORSOURCEMODESET_CREATENEWMODEINFO
 - d3dkmddi/DXGKDDI_MONITORSOURCEMODESET_CREATENEWMODEINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnCreateNewModeInfo
product:
 - Windows
---

# DXGKDDI_MONITORSOURCEMODESET_CREATENEWMODEINFO callback function


## -description

The <b>pfnCreateNewModeInfo</b> function returns a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_monitor_source_mode">D3DKMDT_MONITOR_SOURCE_MODE</a> structure that the display miniport driver populates before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorsourcemodeset_addmode">pfnAddMode</a>.

## -parameters

### -param hMonitorSourceModeSet

[in] A handle to a monitor source mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset">pfnAcquireMonitorSourceModeSet</a> function of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Monitor interface</a>.

### -param ppNewMonitorSourceModeInfo

[out] A pointer to a variable that receives a pointer to a newly created D3DKMDT_MONITOR_SOURCE_MODE structure allocated by the VidPN manager.

## -returns

The <b>pfnCreateNewModeInfo</b> function returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_NO_MEMORY|The function failed because it was unable to allocate enough memory.|

## -remarks

After you call <b>pfnCreateNewModeInfo</b> to obtain a D3DKMDT_MONITOR SOURCE_MODE structure, you must do one, but not both, of the following:

<ul>
<li>
Populate the structure and pass it to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorsourcemodeset_addmode">pfnAddMode</a>.

</li>
<li>
Release the structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorsourcemodeset_releasemodeinfo">pfnReleaseModeInfo</a>.

</li>
</ul>

