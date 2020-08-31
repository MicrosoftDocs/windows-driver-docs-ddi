---
UID: NC:d3dumddi.PFND3DDDI_LOGUMDMARKERCB
title: PFND3DDDI_LOGUMDMARKERCB (d3dumddi.h)
description: Called by the user-mode display driver to log a custom Event Tracing for Windows (ETW) marker event.
old-location: display\pfnlogumdmarkercb.htm
tech.root: display
ms.assetid: BD544686-20D3-4577-9950-9C3B6853C4BD
ms.date: 05/10/2018
keywords: ["PFND3DDDI_LOGUMDMARKERCB callback function"]
ms.keywords: PFND3DDDI_LOGUMDMARKERCB, PFND3DDDI_LOGUMDMARKERCB callback, d3dumddi/pfnLogUMDMarkerCb, display.pfnlogumdmarkercb, pfnLogUMDMarkerCb, pfnLogUMDMarkerCb callback function [Display Devices]
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
 - PFND3DDDI_LOGUMDMARKERCB
 - d3dumddi/PFND3DDDI_LOGUMDMARKERCB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dumddi.h
api_name:
 - pfnLogUMDMarkerCb
product:
 - Windows
---

# PFND3DDDI_LOGUMDMARKERCB callback function


## -description

Called by the user-mode display driver to log a custom Event Tracing for Windows (ETW) marker event.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pLogUMDMarker* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-d3dddicb_logumdmarker">D3DDDICB_LOGUMDMARKER</a> structure that indicates the location of an ETW marker event that is defined by the user-mode display driver.

## -returns

Returns <b>S_OK</b> or an appropriate error result if the function does not complete successfully.

