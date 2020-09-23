---
UID: NC:d3dkmddi.DXGKDDI_VIDPNSOURCEMODESET_PINMODE
title: DXGKDDI_VIDPNSOURCEMODESET_PINMODE (d3dkmddi.h)
description: The pfnPinMode function pins a specified mode in a VidPN source mode set.
old-location: display\dxgk_vidpnsourcemodeset_interface_pfnpinmode.htm
ms.assetid: 14bbdc35-e633-49a5-bdf0-6b60d330ca8e
ms.date: 05/10/2018
keywords: ["DXGKDDI_VIDPNSOURCEMODESET_PINMODE callback function"]
ms.keywords: DXGKDDI_VIDPNSOURCEMODESET_PINMODE, DXGKDDI_VIDPNSOURCEMODESET_PINMODE callback, VidPnFunctions_7fb0636b-da59-4451-8cf2-57b944629499.xml, d3dkmddi/pfnPinMode, display.dxgk_vidpnsourcemodeset_interface_pfnpinmode, pfnPinMode, pfnPinMode callback function [Display Devices]
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
 - DXGKDDI_VIDPNSOURCEMODESET_PINMODE
 - d3dkmddi/DXGKDDI_VIDPNSOURCEMODESET_PINMODE
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

# DXGKDDI_VIDPNSOURCEMODESET_PINMODE callback function


## -description

The <b>pfnPinMode</b> function pins a specified mode in a VidPN source mode set.

## -parameters

### -param hVidPnSourceModeSet

[in] A handle to a VidPN source mode set object. The display miniport driver previously obtained this handle by calling the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_acquiresourcemodeset">pfnAcquireSourceModeSet</a> function of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_vidpn_interface">DXGK_VIDPN_INTERFACE</a> interface.

### -param VidPnSourceModeId

[in] An integer that identifies the mode to be pinned.

## -returns

The <b>pfnPinMode</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN_SOURCEMODESET|The handle supplied in hVidPnSourceModeSet was invalid.|
|STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE_MODE|The mode identified by VidPnSourceModeId does not belong to the source mode set represented by hVidPnSourceModeSet.|

## -remarks

VidPN source mode identifiers are assigned by the operating system. The <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_createnewmodeinfo">pfnCreateNewModeInfo</a> function generates a mode identifier, assigns the identifier to the <b>Id</b> member of a <a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_source_mode">D3DKMDT_VIDPN_SOURCE_MODE</a> structure, and returns the structure to the display miniport driver.

The D3DKMDT_HVIDPNSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_source_mode">D3DKMDT_VIDPN_SOURCE_MODE</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirepinnedmodeinfo">pfnAcquirePinnedModeInfo</a>