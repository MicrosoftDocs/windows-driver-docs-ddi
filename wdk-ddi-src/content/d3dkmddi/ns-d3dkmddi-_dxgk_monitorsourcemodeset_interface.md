---
UID: NS:d3dkmddi._DXGK_MONITORSOURCEMODESET_INTERFACE
title: _DXGK_MONITORSOURCEMODESET_INTERFACE (d3dkmddi.h)
description: The DXGK_MONITORSOURCEMODESET_INTERFACE structure contains pointers to functions that belong to the Monitor Source Mode Set interface, which is implemented by the video present network (VidPN) manager.
old-location: display\dxgk_monitorsourcemodeset_interface.htm
ms.assetid: ceab36a0-3be1-41d8-82c0-8393f93e5f42
ms.date: 05/10/2018
ms.keywords: DXGK_MONITORSOURCEMODESET_INTERFACE, DXGK_MONITORSOURCEMODESET_INTERFACE structure [Display Devices], DmStructs_c4c7e928-09db-424f-8ac7-7efffc71d06e.xml, _DXGK_MONITORSOURCEMODESET_INTERFACE, d3dkmddi/DXGK_MONITORSOURCEMODESET_INTERFACE, display.dxgk_monitorsourcemodeset_interface
ms.topic: struct
f1_keywords:
 - "d3dkmddi/DXGK_MONITORSOURCEMODESET_INTERFACE"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGK_MONITORSOURCEMODESET_INTERFACE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_MONITORSOURCEMODESET_INTERFACE
---

# _DXGK_MONITORSOURCEMODESET_INTERFACE structure


## -description


The DXGK_MONITORSOURCEMODESET_INTERFACE structure contains pointers to functions that belong to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Monitor Source Mode Set interface</a>, which is implemented by the video present network (VidPN) manager.


## -struct-fields




### -field pfnGetNumModes

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorsourcemodeset_getnummodes">pfnGetNumModes</a> function.


### -field pfnAcquirePreferredModeInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorsourcemodeset_acquirepreferredmodeinfo">pfnAcquirePreferredModeInfo</a> function.


### -field pfnAcquireFirstModeInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorsourcemodeset_acquirefirstmodeinfo">pfnAcquireFirstModeInfo</a> function.


### -field pfnAcquireNextModeInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorsourcemodeset_acquirenextmodeinfo">pfnAcquireNextModeInfo</a> function.


### -field pfnCreateNewModeInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorsourcemodeset_createnewmodeinfo">pfnCreateNewModeInfo</a> function.


### -field pfnAddMode

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorsourcemodeset_addmode">pfnAddMode</a> function.


### -field pfnReleaseModeInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_monitorsourcemodeset_releasemodeinfo">pfnReleaseModeInfo</a> function.


## -remarks



The display miniport driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset">pfnAcquireMonitorSourceModeSet</a> function of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Monitor interface</a> to obtain a handle to a monitor source mode set object and a pointer to a DXGK_MONITORSOURCEMODESET_INTERFACE structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the monitor source mode set object.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_d3dkmdt_monitor_source_mode">D3DKMDT_MONITOR_SOURCE_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_vidpnsourcemodeset_interface">DXGK_VIDPNSOURCEMODESET_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_vidpntargetmodeset_interface">DXGK_VIDPNTARGETMODESET_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset">pfnAcquireMonitorSourceModeSet</a>
 

 

