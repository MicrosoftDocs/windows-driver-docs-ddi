---
UID: NC:d3dumddi.PFND3DDDI_FLIPOVERLAY
title: PFND3DDDI_FLIPOVERLAY (d3dumddi.h)
description: The FlipOverlay function causes the overlay hardware to start displaying the given new allocation.
old-location: display\flipoverlay.htm
tech.root: display
ms.assetid: 8490ebdd-f993-4c77-b6da-d57ef5e5d05f
ms.date: 05/10/2018
ms.keywords: FlipOverlay, FlipOverlay callback function [Display Devices], PFND3DDDI_FLIPOVERLAY, PFND3DDDI_FLIPOVERLAY callback, UserModeDisplayDriver_Functions_4a2c5f7b-8d52-465f-84ea-a1fc4f53381b.xml, d3dumddi/FlipOverlay, display.flipoverlay
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
 - "d3dumddi/FlipOverlay"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - FlipOverlay
product:
 - Windows
---

# PFND3DDDI_FLIPOVERLAY callback function

## -description

The <i>FlipOverlay</i> function causes the overlay hardware to start displaying the given new allocation.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_flipoverlay">D3DDDIARG_FLIPOVERLAY</a> structure that describes the new allocation to display by using the overlay.

## -returns

<i>FlipOverlay</i> returns S_OK or an appropriate error result if the new allocation is not successfully displayed.

## -remarks

Overlays are independent from the resources that are displayed by using the overlays.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_flipoverlay">D3DDDIARG_FLIPOVERLAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

