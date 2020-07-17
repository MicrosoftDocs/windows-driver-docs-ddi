---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTARGETMODESET_PINMODE
title: DXGKDDI_VIDPNTARGETMODESET_PINMODE (d3dkmddi.h)
description: The pfnPinMode function pins a specified mode in a VidPN target mode set.
old-location: display\dxgk_vidpntargetmodeset_interface_pfnpinmode.htm
ms.assetid: 91ea3105-2fdf-4533-a2d4-d27f1e660056
ms.date: 05/10/2018
keywords: ["DXGKDDI_VIDPNTARGETMODESET_PINMODE callback function"]
ms.keywords: DXGKDDI_VIDPNTARGETMODESET_PINMODE, DXGKDDI_VIDPNTARGETMODESET_PINMODE callback, VidPnFunctions_2b6f869f-bd7d-4699-8934-04cbe56bf0af.xml, d3dkmddi/pfnPinMode, display.dxgk_vidpntargetmodeset_interface_pfnpinmode, pfnPinMode, pfnPinMode callback function [Display Devices]
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
 - "d3dkmddi/pfnPinMode"
 - "pfnPinMode"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnPinMode
product:
 - Windows
---

# DXGKDDI_VIDPNTARGETMODESET_PINMODE callback function

## -description

The <b>pfnPinMode</b> function pins a specified mode in a VidPN target mode set.

## -parameters

### -param hVidPnTargetModeSet

[in] A handle to a VidPN target mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_acquiretargetmodeset">pfnAcquireTargetModeSet</a> function of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_vidpn_interface">DXGK_VIDPN_INTERFACE</a> interface.

### -param VidPnTargetModeId

[in] An integer that identifies the mode to be pinned.

## -returns

The <b>pfnPinMode</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN_TARGETMODESET|The handle supplied in hVidPnTargetModeSet was invalid.|
|STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET_MODE|The mode identified by VidPnTargetModeId does not belong to the source mode set represented by hVidPnTargetModeSet.|

## -remarks

VidPN target mode identifiers are assigned by the operating system. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_createnewmodeinfo">pfnCreateNewModeInfo</a> function generates a mode identifier, assigns the identifier to the <b>Id</b> member of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_target_mode">D3DKMDT_VIDPN_TARGET_MODE</a> structure, and returns the structure to the display miniport driver.

The D3DKMDT_HVIDPNTARGETMODESET data type is defined in <i>D3dkmdt.h</i>.

