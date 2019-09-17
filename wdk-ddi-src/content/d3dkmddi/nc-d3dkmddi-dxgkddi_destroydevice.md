---
UID: NC:d3dkmddi.DXGKDDI_DESTROYDEVICE
title: DXGKDDI_DESTROYDEVICE (d3dkmddi.h)
description: The DxgkDdiDestroyDevice function destroys a graphics context device.
old-location: display\dxgkddidestroydevice.htm
ms.assetid: c067fe92-2364-4122-a7ed-03df7906ae64
ms.date: 05/10/2018
ms.keywords: DXGKDDI_DESTROYDEVICE, DXGKDDI_DESTROYDEVICE callback, DmFunctions_14927367-d2f9-4aa4-ab3d-a3c8decedbcf.xml, DxgkDdiDestroyDevice, DxgkDdiDestroyDevice callback function [Display Devices], d3dkmddi/DxgkDdiDestroyDevice, display.dxgkddidestroydevice
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
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
 - "d3dkmddi/DxgkDdiDestroyDevice"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiDestroyDevice
product:
 - Windows
---

# DXGKDDI_DESTROYDEVICE callback function

## -description

The <i>DxgkDdiDestroyDevice</i> function destroys a graphics context device.

## -parameters

### -param hDevice

[in] A handle to the graphics context device that <i>DxgkDdiDestroyDevice</i> will destroy. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_createdevice">DxgkDdiCreateDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <b>hDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_createdevice">DXGKARG_CREATEDEVICE</a> structure.

## -returns

<i>DxgkDdiDestroyDevice</i> returns STATUS_SUCCESS, or an appropriate error result if the graphics context device is not successfully destroyed.

## -remarks

The DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiDestroyDevice</i> function to destroy a graphics context device that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_createdevice">DxgkDdiCreateDevice</a> function created. <i>DxgkDdiDestroyDevice</i> should free all of the resources that were allocated for the device and clean up any internal tracking data structures. 

<i>DxgkDdiDestroyDevice</i> should be made pageable.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_createdevice">DXGKARG_CREATEDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_createdevice">DxgkDdiCreateDevice</a>

