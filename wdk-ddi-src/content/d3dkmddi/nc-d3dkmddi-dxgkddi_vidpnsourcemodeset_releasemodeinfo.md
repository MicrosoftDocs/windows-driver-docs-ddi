---
UID: NC:d3dkmddi.DXGKDDI_VIDPNSOURCEMODESET_RELEASEMODEINFO
title: DXGKDDI_VIDPNSOURCEMODESET_RELEASEMODEINFO (d3dkmddi.h)
description: The pfnReleaseModeInfo function releases a D3DKMDT_VIDPN_SOURCE_MODE structure that the VidPN manager previously provided to the display miniport driver.
old-location: display\dxgk_vidpnsourcemodeset_interface_pfnreleasemodeinfo.htm
ms.assetid: 614283cc-90bf-44f2-bab2-1aeec5e7de01
ms.date: 05/10/2018
ms.keywords: DXGKDDI_VIDPNSOURCEMODESET_RELEASEMODEINFO, DXGKDDI_VIDPNSOURCEMODESET_RELEASEMODEINFO callback, VidPnFunctions_4516c897-bcf8-4a32-9517-45c86690d746.xml, d3dkmddi/pfnReleaseModeInfo, display.dxgk_vidpnsourcemodeset_interface_pfnreleasemodeinfo, pfnReleaseModeInfo, pfnReleaseModeInfo callback function [Display Devices]
ms.topic: callback
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dkmddi.h
api_name:
- pfnReleaseModeInfo
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_VIDPNSOURCEMODESET_RELEASEMODEINFO callback function


## -description


The <b>pfnReleaseModeInfo</b> function releases a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_source_mode">D3DKMDT_VIDPN_SOURCE_MODE</a> structure that the VidPN manager previously provided to the display miniport driver.


## -parameters




### -param hVidPnSourceModeSet [in]

[in] A handle to a VidPN source mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_acquiresourcemodeset">pfnAcquireSourceModeSet</a> function of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_vidpn_interface">DXGK_VIDPN_INTERFACE</a> interface.


### -param pVidPnSourceModeInfo [in]

[in] A pointer to the D3DKMDT_VIDPN_SOURCE_MODE structure that is to be released.


## -returns



The <b>pfnReleaseModeInfo</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN_SOURCEMODESET|The handle supplied in hVidPnSourceModeSet was invalid.|
|STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE_MODE|The pointer supplied in pVidPnSourceModeInfo was invalid.|



## -remarks



When you have finished using a D3DKMDT_VIDPN_SOURCE_MODE structure that you obtained by calling any of the following functions, you must release the structure by calling <b>pfnReleaseModeInfo</b>.

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirefirstmodeinfo">pfnAcquireFirstModeInfo</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirenextmodeinfo">pfnAcquireNextModeInfo</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirepinnedmodeinfo">pfnAcquirePinnedModeInfo</a>


</li>
</ul>
If you obtain a D3DKMDT_VIDPN_SOURCE_MODE structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_createnewmodeinfo">pfnCreateNewModeInfo</a> and then pass that structure to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_addmode">pfnAddMode</a>, you do not need to release the structure.

If you obtain a handle by calling <b>pfnCreateNewModeInfo</b> and then you decide not to add the new mode to a source mode set, you must release the newly created structure by calling <b>pfnReleaseModeInfo</b>.

The D3DKMDT_HVIDPNSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_source_mode">D3DKMDT_VIDPN_SOURCE_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirefirstmodeinfo">pfnAcquireFirstModeInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirenextmodeinfo">pfnAcquireNextModeInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirepinnedmodeinfo">pfnAcquirePinnedModeInfo</a>
 

 

