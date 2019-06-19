---
UID: NC:d3dkmddi.DXGKDDI_MONITORSOURCEMODESET_ADDMODE
title: DXGKDDI_MONITORSOURCEMODESET_ADDMODE (d3dkmddi.h)
description: The pfnAddMode function adds a monitor source mode to a specified monitor source mode set object.
old-location: display\dxgk_monitorsourcemodeset_interface_pfnaddmode.htm
ms.assetid: 88fe5a2d-d140-4ebc-846d-acea39b8bc73
ms.date: 05/10/2018
ms.keywords: DXGKDDI_MONITORSOURCEMODESET_ADDMODE, DXGKDDI_MONITORSOURCEMODESET_ADDMODE callback, VidPnFunctions_1b037d93-a615-41e1-bc22-bf9565050062.xml, d3dkmddi/pfnAddMode, display.dxgk_monitorsourcemodeset_interface_pfnaddmode, pfnAddMode, pfnAddMode callback function [Display Devices]
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dkmddi.h
api_name:
- pfnAddMode
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_MONITORSOURCEMODESET_ADDMODE callback function


## -description


The <b>pfnAddMode</b> function adds a monitor source mode to a specified monitor source mode set object.


## -parameters




### -param hMonitorSourceModeSet [in]

[in] A handle to a monitor source mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/a64197c0-a61f-4989-9b68-4e06b1a69fd4">pfnAcquireMonitorSourceModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor interface</a>.


### -param pMonitorSourceModeInfo [in]

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546133">D3DKMDT_MONITOR_SOURCE_MODE</a> structure that describes the monitor source mode. The display miniport driver previously obtained this structure by calling <a href="https://msdn.microsoft.com/314b345c-a40b-418d-a2d8-c7b42e5fd27d">pfnCreateNewModeInfo</a>.


## -returns



The <b>pfnAddMode</b> function returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_NO_MEMORY|The function failed because it could not allocate enough memory.|
|STATUS_GRAPHICS_INVALID_MONITOR_SOURCE_MODE|The information supplied in pMonitorSourceModeInfo was invalid.|
|STATUS_GRAPHICS_INVALID_MONITOR_SOURCEMODESET|The handle supplied in hMonitorSourceModeSet was invalid.|
|STATUS_GRAPHICS_INVALID_FREQUENCY|The frequency information supplied in pMonitorSourceModeInfo was invalid.|
|STATUS_GRAPHICS_INVALID_ACTIVE_REGION|The active region supplied in pMonitorSourceModeInfo was invalid.|
|STATUS_GRAPHICS_INVALID_TOTAL_REGION|The total region supplied in pMonitorSourceModeInfo was invalid.|
|STATUS_GRAPHICS_MODE_ALREADY_IN_MODE_SET|The mode set already contains a mode that is identical to the mode supplied in pMonitorSourceModeInfo.|
|STATUS_GRAPHICS_MODE_ID_MUST_BE_UNIQUE|The identifier supplied in pMonitorSourceModeInfo->Id is already being used for another mode in the mode set.|
|STATUS_GRAPHICS_RESOURCES_NOT_RELATED|The structure pointed to by pMonitorSourceModeInfo was not created for addition to the mode set specified by hMonitorSourceModeSet.|
 




## -remarks



If <i>pMonitorSourceModeInfo</i>-><b>Preference</b> is equal to D3DKMDT_MP_PREFERRED, the newly added mode becomes the preferred mode of the mode set.




## -see-also




<a href="https://msdn.microsoft.com/314b345c-a40b-418d-a2d8-c7b42e5fd27d">pfnCreateNewModeInfo</a>
 

 

