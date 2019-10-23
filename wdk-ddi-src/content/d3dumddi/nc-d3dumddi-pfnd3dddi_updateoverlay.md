---
UID: NC:d3dumddi.PFND3DDDI_UPDATEOVERLAY
title: PFND3DDDI_UPDATEOVERLAY (d3dumddi.h)
description: The UpdateOverlay function reconfigures or moves an overlay that is being displayed.
old-location: display\updateoverlay.htm
tech.root: display
ms.assetid: 80d7cc5c-51d8-4b91-9581-b073f9b0e68a
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_UPDATEOVERLAY, PFND3DDDI_UPDATEOVERLAY callback, UpdateOverlay, UpdateOverlay callback function [Display Devices], UserModeDisplayDriver_Functions_58c588ce-de18-4aa0-bb22-0c33d053e22f.xml, d3dumddi/UpdateOverlay, display.updateoverlay
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.typenames: 
f1_keywords:
 - "d3dumddi/UpdateOverlay"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - UpdateOverlay
product:
 - Windows
---

# PFND3DDDI_UPDATEOVERLAY callback function

## -description

The <i>UpdateOverlay</i> function reconfigures or moves an overlay that is being displayed.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_updateoverlay">D3DDDIARG_UPDATEOVERLAY</a> structure that describes how to reconfigure the overlay.

## -returns

<i>UpdateOverlay</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The overlay is successfully modified.|
|E_OUTOFMEMORY|UpdateOverlay could not complete because of insufficient memory.|
|D3DDDIERR_NOTAVAILABLE|UpdateOverlay could not complete because insufficient bandwidth was available or the requested overlay hardware was unavailable.|
|D3DDDIERR_UNSUPPORTEDOVERLAYFORMAT|The specified overlay format is not supported by the overlay hardware.|
|D3DDDIERR_UNSUPPORTEDOVERLAY|The overlay hardware is not supported for the specified size and display mode.|

## -remarks

Overlays are independent from the resources that are displayed by using the overlays.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_updateoverlay">D3DDDIARG_UPDATEOVERLAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

