---
UID: NC:d3dkmddi.DXGKDDI_VIDPNSOURCEMODESET_ADDMODE
title: DXGKDDI_VIDPNSOURCEMODESET_ADDMODE (d3dkmddi.h)
description: The pfnAddMode function adds a VidPN source mode to a specified VidPN source mode set object.
old-location: display\dxgk_vidpnsourcemodeset_interface_pfnaddmode.htm
ms.assetid: 754078c2-f79b-4237-a14c-96903856f3a5
ms.date: 05/10/2018
keywords: ["DXGKDDI_VIDPNSOURCEMODESET_ADDMODE callback function"]
ms.keywords: DXGKDDI_VIDPNSOURCEMODESET_ADDMODE, DXGKDDI_VIDPNSOURCEMODESET_ADDMODE callback, VidPnFunctions_4a5d2191-c7d3-4b94-80aa-b6b3c71dfe18.xml, d3dkmddi/pfnAddMode, display.dxgk_vidpnsourcemodeset_interface_pfnaddmode, pfnAddMode, pfnAddMode callback function [Display Devices]
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
 - "d3dkmddi/pfnAddMode"
 - "pfnAddMode"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnAddMode
product:
 - Windows
---

# DXGKDDI_VIDPNSOURCEMODESET_ADDMODE callback function

## -description

The <b>pfnAddMode</b> function adds a VidPN source mode to a specified VidPN source mode set object.

## -parameters

### -param hVidPnSourceModeSet

[in] A handle to a VidPN source mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_acquiresourcemodeset">pfnAcquireSourceModeSet</a> function of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_vidpn_interface">DXGK_VIDPN_INTERFACE</a> interface.

### -param pVidPnSourceModeInfo

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_source_mode">D3DKMDT_VIDPN_SOURCE_MODE</a> structure that describes the source mode. The display miniport driver previously obtained this structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_createnewmodeinfo">pfnCreateNewModeInfo</a>.

## -returns

The <b>pfnAddMode</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN_SOURCEMODESET|The handle supplied in hVidPnSourceModeSet was invalid.|

## -remarks

To add a mode to a source mode set, the display miniport driver performs the following steps.

Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_createnewmodeinfo">pfnCreateNewModeInfo</a> to obtain a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_source_mode">D3DKMDT_VIDPN_SOURCE_MODE</a> structure. The <b>pnfCreateNewModeInfo</b> function allocates the structure, fills in the <b>Id</b> member with a newly generated source mode identifier, and sets the <b>Type</b> member to <b>D3DKMDT_RMT_UNINITIALIZED</b>.

Populate the D3DKMDT_VIDPN_SOURCE_MODE structure (except for the <b>Id</b> member) with information about the mode, including the mode's type and format.

Call <b>pfnAddMode</b> to add the mode to a source mode set. 

The VidPN manager allocates a D3DKMDT_VIDPN_SOURCE_MODE structure when you call <b>pfnCreateNewModeInfo</b>. If you add the mode described by that structure to a source mode set, you do not need to explicitly release the structure; <b>pfnAddMode</b> releases it.

If you obtain a D3DKMDT_VIDPN_SOURCE_MODE structure by calling <b>pfnCreateNewModeInfo</b> and then decide not to add that mode to a source mode set, you must explicity release the structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_releasemodeinfo">pfnReleaseModeInfo</a>.

The D3DKMDT_HVIDPNSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_source_mode">D3DKMDT_VIDPN_SOURCE_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_createnewmodeinfo">pfnCreateNewModeInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_releasemodeinfo">pfnReleaseModeInfo</a>

