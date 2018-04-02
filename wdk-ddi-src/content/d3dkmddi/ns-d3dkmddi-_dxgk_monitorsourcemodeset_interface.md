---
UID: NS:d3dkmddi._DXGK_MONITORSOURCEMODESET_INTERFACE
title: "_DXGK_MONITORSOURCEMODESET_INTERFACE"
author: windows-driver-content
description: The DXGK_MONITORSOURCEMODESET_INTERFACE structure contains pointers to functions that belong to the Monitor Source Mode Set interface, which is implemented by the video present network (VidPN) manager.
old-location: display\dxgk_monitorsourcemodeset_interface.htm
old-project: display
ms.assetid: ceab36a0-3be1-41d8-82c0-8393f93e5f42
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_MONITORSOURCEMODESET_INTERFACE, DXGK_MONITORSOURCEMODESET_INTERFACE structure [Display Devices], DmStructs_c4c7e928-09db-424f-8ac7-7efffc71d06e.xml, _DXGK_MONITORSOURCEMODESET_INTERFACE, d3dkmddi/DXGK_MONITORSOURCEMODESET_INTERFACE, display.dxgk_monitorsourcemodeset_interface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_MONITORSOURCEMODESET_INTERFACE
product: Windows
targetos: Windows
req.typenames: DXGK_MONITORSOURCEMODESET_INTERFACE
---

# _DXGK_MONITORSOURCEMODESET_INTERFACE structure


## -description


The DXGK_MONITORSOURCEMODESET_INTERFACE structure contains pointers to functions that belong to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568435">Monitor Source Mode Set interface</a>, which is implemented by the video present network (VidPN) manager.


## -struct-fields




### -field pfnGetNumModes

A pointer to the <a href="https://msdn.microsoft.com/58daf5be-45c5-493b-9d51-ef48bb123dce">pfnGetNumModes</a> function.


### -field pfnAcquirePreferredModeInfo

A pointer to the <a href="https://msdn.microsoft.com/80d3d199-42ad-4f21-8122-05dfad37016d">pfnAcquirePreferredModeInfo</a> function.


### -field pfnAcquireFirstModeInfo

A pointer to the <a href="https://msdn.microsoft.com/d448c3f4-7adb-4ceb-8c42-8cba3d2cfeae">pfnAcquireFirstModeInfo</a> function.


### -field pfnAcquireNextModeInfo

A pointer to the <a href="https://msdn.microsoft.com/55c629c5-1d73-40dd-a5aa-73ddcc5236b5">pfnAcquireNextModeInfo</a> function.


### -field pfnCreateNewModeInfo

A pointer to the <a href="https://msdn.microsoft.com/314b345c-a40b-418d-a2d8-c7b42e5fd27d">pfnCreateNewModeInfo</a> function.


### -field pfnAddMode

A pointer to the <a href="https://msdn.microsoft.com/88fe5a2d-d140-4ebc-846d-acea39b8bc73">pfnAddMode</a> function.


### -field pfnReleaseModeInfo

A pointer to the <a href="https://msdn.microsoft.com/2c82ec09-e858-4efc-a1c0-a3792e0b5ddf">pfnReleaseModeInfo</a> function.


## -remarks



The display miniport driver calls the <a href="https://msdn.microsoft.com/a64197c0-a61f-4989-9b68-4e06b1a69fd4">pfnAcquireMonitorSourceModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor interface</a> to obtain a handle to a monitor source mode set object and a pointer to a DXGK_MONITORSOURCEMODESET_INTERFACE structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the monitor source mode set object.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546133">D3DKMDT_MONITOR_SOURCE_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562073">DXGK_VIDPNSOURCEMODESET_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562082">DXGK_VIDPNTARGETMODESET_INTERFACE</a>



<a href="https://msdn.microsoft.com/a64197c0-a61f-4989-9b68-4e06b1a69fd4">pfnAcquireMonitorSourceModeSet</a>
 

 

