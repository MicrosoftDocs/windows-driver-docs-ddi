---
UID: NC:d3d10umddi.PFND3D10DDI_CREATEELEMENTLAYOUT
title: PFND3D10DDI_CREATEELEMENTLAYOUT (d3d10umddi.h)
description: The CreateElementLayout function creates an element layout.
old-location: display\createelementlayout.htm
ms.assetid: 5af2189a-a064-4c62-be09-733c1d632983
ms.date: 05/10/2018
ms.keywords: CreateElementLayout, CreateElementLayout callback function [Display Devices], PFND3D10DDI_CREATEELEMENTLAYOUT, PFND3D10DDI_CREATEELEMENTLAYOUT callback, UserModeDisplayDriverDx10_Functions_ca001144-74f8-4ff7-9cce-664d4070ad3d.xml, d3d10umddi/CreateElementLayout, display.createelementlayout
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
 - "d3d10umddi/CreateElementLayout"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CreateElementLayout
product:
 - Windows
---

# PFND3D10DDI_CREATEELEMENTLAYOUT callback function

## -description

The <b>CreateElementLayout</b> function creates an element layout.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCreateElementLayout* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createelementlayout">D3D10DDIARG_CREATEELEMENTLAYOUT</a> structure that describes the parameters that the user-mode display driver uses to create an element layout.

### -param Arg3

*hElementLayout* [in]

A handle to the driver's private data for the element layout.

### -param Arg4

*hRTElementLayout* [in]

A handle to the element layout that the driver should use anytime it calls back into the Direct3D runtime.

## -remarks

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 

The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyelementlayout">DestroyElementLayout</a> function to destroy the handle that the <i>hElementLayout</i> parameter specifies.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivateelementlayoutsize">CalcPrivateElementLayoutSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createelementlayout">D3D10DDIARG_CREATEELEMENTLAYOUT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyelementlayout">DestroyElementLayout</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

