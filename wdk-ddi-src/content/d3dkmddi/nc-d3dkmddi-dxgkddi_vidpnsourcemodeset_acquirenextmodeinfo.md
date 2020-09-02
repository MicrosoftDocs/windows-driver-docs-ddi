---
UID: NC:d3dkmddi.DXGKDDI_VIDPNSOURCEMODESET_ACQUIRENEXTMODEINFO
title: DXGKDDI_VIDPNSOURCEMODESET_ACQUIRENEXTMODEINFO (d3dkmddi.h)
description: The pfnAcquireNextModeInfo function returns a descriptor of the next mode in a specified VidPN source mode set, given the current mode.
old-location: display\dxgk_vidpnsourcemodeset_interface_pfnacquirenextmodeinfo.htm
ms.assetid: d9cb1ff1-c428-46e5-884a-5fc39e16300e
ms.date: 05/10/2018
keywords: ["DXGKDDI_VIDPNSOURCEMODESET_ACQUIRENEXTMODEINFO callback function"]
ms.keywords: DXGKDDI_VIDPNSOURCEMODESET_ACQUIRENEXTMODEINFO, DXGKDDI_VIDPNSOURCEMODESET_ACQUIRENEXTMODEINFO callback, VidPnFunctions_d74c5638-dbfc-4d3b-8db3-ac1723d082aa.xml, d3dkmddi/pfnAcquireNextModeInfo, display.dxgk_vidpnsourcemodeset_interface_pfnacquirenextmodeinfo, pfnAcquireNextModeInfo, pfnAcquireNextModeInfo callback function [Display Devices]
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
 - DXGKDDI_VIDPNSOURCEMODESET_ACQUIRENEXTMODEINFO
 - d3dkmddi/DXGKDDI_VIDPNSOURCEMODESET_ACQUIRENEXTMODEINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnAcquireNextModeInfo
product:
 - Windows
---

# DXGKDDI_VIDPNSOURCEMODESET_ACQUIRENEXTMODEINFO callback function


## -description

The <b>pfnAcquireNextModeInfo</b> function returns a descriptor of the next mode in a specified VidPN source mode set, given the current mode.

## -parameters

### -param hVidPnSourceModeSet

[in] A handle to a VidPN source mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_acquiresourcemodeset">pfnAcquireSourceModeSet</a> function of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_vidpn_interface">DXGK_VIDPN_INTERFACE</a> interface.

### -param pVidPnSourceModeInfo

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_source_mode">D3DKMDT_VIDPN_SOURCE_MODE</a> structure that describes the current mode. The display miniport driver previously obtained this pointer by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirefirstmodeinfo">pfnAcquireFirstModeInfo</a> or <b>pfnAcquireNextModeInfo</b>.

### -param ppNextVidPnSourceModeInfo

[out] A pointer to a variable that receives a pointer to a D3DKMDT_VIDPN_SOURCE_MODE structure that describes the next mode.

## -returns

The <b>pfnAcquireNextModeInfo</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN_SOURCEMODESET|The handle supplied in hVidPnSourceModeSet was invalid.|

## -remarks

When you have finished using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_source_mode">D3DKMDT_VIDPN_SOURCE_MODE</a> structure, you must release the structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_releasemodeinfo">pfnReleaseModeInfo</a>.

You can enumerate all the modes that belong to a VidPN source mode set object by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirefirstmodeinfo">pfnAcquireFirstModeInfo</a> and then making a sequence of calls to <b>pfnAcquireNextModeInfo</b>.

The D3DKMDT_HVIDPNSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_source_mode">D3DKMDT_VIDPN_SOURCE_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirefirstmodeinfo">pfnAcquireFirstModeInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_releasemodeinfo">pfnReleaseModeInfo</a>

