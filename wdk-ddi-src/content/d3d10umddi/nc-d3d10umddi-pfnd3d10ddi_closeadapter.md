---
UID: NC:d3d10umddi.PFND3D10DDI_CLOSEADAPTER
title: PFND3D10DDI_CLOSEADAPTER (d3d10umddi.h)
description: The CloseAdapter(D3D10) function releases resources for a graphics adapter object.
old-location: display\closeadapter_d3d10_.htm
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_CLOSEADAPTER callback function"]
ms.keywords: CloseAdapter, CloseAdapter callback function [Display Devices], PFND3D10DDI_CLOSEADAPTER, PFND3D10DDI_CLOSEADAPTER callback, UserModeDisplayDriverDx10_Functions_0adac9d0-3334-4bee-86ef-4e1450b1feb0.xml, d3d10umddi/CloseAdapter, display.closeadapter_d3d10_
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D10DDI_CLOSEADAPTER
 - d3d10umddi/PFND3D10DDI_CLOSEADAPTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3D10DDI_CLOSEADAPTER
---

# PFND3D10DDI_CLOSEADAPTER callback function


## -description

The <b>CloseAdapter(D3D10)</b> function releases resources for a graphics adapter object.

## -parameters

### -param Arg1

*hAdapter* [in]

A handle to the graphics adapter object that was created with the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_openadapter">OpenAdapter10</a> function.

## -returns

<b>CloseAdapter(D3D10)</b> returns S_OK if the operation succeeds. Otherwise, this function returns an appropriate error result.

## -remarks

The user-mode display driver's <b>CloseAdapter(D3D10)</b> function should free all of the resources that the driver allocated for the graphics adapter object.

Before <b>CloseAdapter(D3D10)</b> closes the graphics adapter object, all of the display devices that were created by using the graphics adapter object in calls to the user-mode display driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function will be destroyed in calls to the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroydevice">DestroyDevice(D3D10)</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_adapterfuncs">D3D10DDI_ADAPTERFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroydevice">DestroyDevice(D3D10)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_openadapter">OpenAdapter10</a>

