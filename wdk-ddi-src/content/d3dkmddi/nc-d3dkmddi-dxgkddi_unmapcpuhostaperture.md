---
UID: NC:d3dkmddi.DXGKDDI_UNMAPCPUHOSTAPERTURE
title: DXGKDDI_UNMAPCPUHOSTAPERTURE (d3dkmddi.h)
description: DxgkDdiUnmapCpuHostAperture is used to unmap a previously mapped range of the CPU host aperture.
old-location: display\dxgkddiunmapcpuhostaperture.htm
ms.assetid: AFE6B92F-49DB-47F9-90BC-F75B5F37178D
ms.date: 05/10/2018
ms.keywords: DXGKDDI_UNMAPCPUHOSTAPERTURE, DXGKDDI_UNMAPCPUHOSTAPERTURE callback, DxgkDdiUnmapCpuHostAperture, DxgkDdiUnmapCpuHostAperture callback function [Display Devices], d3dkmddi/DxgkDdiUnmapCpuHostAperture, display.dxgkddiunmapcpuhostaperture
f1_keywords:
 - "d3dkmddi/DxgkDdiUnmapCpuHostAperture"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- UserDefined
api_location:
- d3dkmddi.h
api_name:
- DxgkDdiUnmapCpuHostAperture
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_UNMAPCPUHOSTAPERTURE callback function


## -description


<b>DxgkDdiUnmapCpuHostAperture</b> is used to unmap a previously mapped range of the CPU host aperture.


## -parameters




### -param hAdapter

A handle to the display adapter.


### -param pArgs

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_unmapcpuhostaperture">DXGKARG_UNMAPCPUHOSTAPERTURE</a> structure that describes the operation.


## -returns




      Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes defined in <b>Ntstatus.h</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_unmapcpuhostaperture">DXGKARG_UNMAPCPUHOSTAPERTURE</a>
 

 

