---
UID: NS:dxgiddi._DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS
title: "_DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS"
author: windows-driver-content
description: Used in a call to the pfnGetMultiplaneOverlayGroupCaps function to get a group of overlay plane capabilities.
old-location: display\dxgi_ddi_arg_getmultiplaneoverlaygroupcaps.htm
old-project: display
ms.assetid: C63125FA-7ADF-406A-A729-67C6ACA47D96
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS, DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS structure [Display Devices], _DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS, display.dxgi_ddi_arg_getmultiplaneoverlaygroupcaps, dxgiddi/DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Dxgiddi.h
api_name:
-	DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS
product:
- Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS
---

# _DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS structure


## -description


Used in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265494">pfnGetMultiplaneOverlayGroupCaps</a> function to get a group of overlay plane capabilities.


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) for which overlay plane capabilities are needed.

The Direct3D runtime passed this handle to the driver in the <b>hDrvDevice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541664">D3D10DDIARG_CREATEDEVICE</a> structure when it created the device by calling the <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> routine.


### -field VidPnSourceId

[in] The zero-based video present network (VidPN) source identification number of the input for which the capabilities are queried.


### -field GroupIndex

[in] The index of the overlay capability group for which capabilities are queried. This value is always between zero and (<a href="https://msdn.microsoft.com/library/windows/hardware/hh780285">DXGI_DDI_MULTIPLANE_OVERLAY_CAPS</a>.<b>NumCapabilityGroups</b> – 1).


### -field MultiplaneOverlayGroupCaps

[out] The overlay plane capabilities for the requested capability group, given as a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265376">DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS</a> structure.


## -see-also




<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541664">D3D10DDIARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh780285">DXGI_DDI_MULTIPLANE_OVERLAY_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265376">DXGI_DDI_MULTIPLANE_OVERLAY_GROUP_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265494">pfnGetMultiplaneOverlayGroupCaps</a>
 

 

