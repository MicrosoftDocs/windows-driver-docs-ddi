---
UID: NC:d3dumddi.PFND3DDDI_CHECKPRESENTDURATIONSUPPORT
title: PFND3DDDI_CHECKPRESENTDURATIONSUPPORT (d3dumddi.h)
description: Called by the Microsoft Direct3D runtime to request that the user-mode display driver get hardware device capabilities for seamlessly switching to a new monitor refresh rate.
old-location: display\checkpresentdurationsupport.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_CHECKPRESENTDURATIONSUPPORT callback function"]
ms.keywords: CheckPresentDurationSupport, CheckPresentDurationSupport callback function [Display Devices], PFND3DDDI_CHECKPRESENTDURATIONSUPPORT, PFND3DDDI_CHECKPRESENTDURATIONSUPPORT callback, d3dumddi/CheckPresentDurationSupport, display.checkpresentdurationsupport
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFND3DDDI_CHECKPRESENTDURATIONSUPPORT
 - d3dumddi/PFND3DDDI_CHECKPRESENTDURATIONSUPPORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dumddi.h
api_name:
 - PFND3DDDI_CHECKPRESENTDURATIONSUPPORT
---

# PFND3DDDI_CHECKPRESENTDURATIONSUPPORT callback function


## -description

Called by the Microsoft Direct3D runtime to request that the user-mode display driver  get  hardware device capabilities for seamlessly switching to a new monitor refresh rate. Optionally implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param unnamedParam2

*pPresentDurationSupport* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-d3dddiarg_checkpresentdurationsupport">D3DDDIARG_CHECKPRESENTDURATIONSUPPORT</a> structure that contains info on hardware device support for seamlessly switching to a new monitor refresh rate.

## -returns

If this routine succeeds, it returns <b>S_OK</b>. The driver should always return a success code.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-d3dddiarg_checkpresentdurationsupport">D3DDDIARG_CHECKPRESENTDURATIONSUPPORT</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

